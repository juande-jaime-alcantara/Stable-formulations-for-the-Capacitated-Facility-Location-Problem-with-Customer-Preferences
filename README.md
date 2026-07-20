<!DOCTYPE html>
<html lang="en">

<h1>Stable formulations for the Capacitated Facility Location Problem with Customer Preferences — Supporting Material</h1>

[![DOI](https://zenodo.org/badge/1161805685.svg)](https://doi.org/10.5281/zenodo.19127602)

<p>This repository contains the supplementary material associated with the article:</p>

<p><strong><em>“Stable formulations for the Capacitated Facility Location Problem with Customer Preferences”</em></strong></p>

<p>
<strong>Authors</strong><br>
Concepción Domínguez – University of Murcia (UM), Spain<br>
Juan de Dios Jaime-Alcántara – University of Murcia (UM), Spain
</p>

<hr>

<h2>📁 Repository structure</h2>

<pre><code>instances/
  1/
  2/
models/
solutions/
README.md
</code></pre>

<ul>
  <li><code>instances/1/</code>: randomly generated instances used in the computational experiments described in this repository.</li>
  <li><code>instances/2/</code>: Calvete instances provided in their original format.</li>
  <li><code>models/</code>: Mosel/Xpress model files implementing the MILP formulations presented in the paper.</li>
  <li><code>solutions/</code>: solution files associated with the tested instances.</li>
  <li><code>README.md</code>: description of the repository structure, instance formats, solution format, and usage instructions.</li>
</ul>

<hr>

<h2>📄 Instance formats</h2>

<p>The folder <code>instances/</code> contains two subfolders with different instance sets and formats.</p>

<h3>Instances in <code>instances/1/</code></h3>

<p>These instances follow the naming format:</p>

<pre><code>CSPLPO_n_m_q_s.dat
</code></pre>

<h4>Naming convention</h4>

<ul>
  <li><code>n</code>: number of customers</li>
  <li><code>m</code>: number of facilities</li>
  <li><code>q</code>: capacity assigned to each facility</li>
  <li><code>s</code>: instance index (five instances are provided for each parameter tuple)</li>
</ul>

<p>Example:</p>

<pre><code>CSPLPO_50_5_12_1.dat
</code></pre>

<h4>File structure</h4>

<p>Each instance is provided in plain text format and contains:</p>

<ul>
  <li><code>nI</code>: number of customers</li>
  <li><code>nJ</code>: number of facilities</li>
  <li><code>CapsJ</code>: common capacity parameter used in the generation</li>
  <li><code>nIns</code>: instance index</li>
  <li><code>CostJ</code>: opening cost of each facility</li>
  <li><code>CapJ</code>: vector of facility capacities</li>
  <li><code>CostIJ</code>: assignment cost matrix</li>
  <li><code>Pref</code>: strict preference ranking of facilities for each customer</li>
</ul>

<p>General structure:</p>

<pre><code>nI: &lt;number_of_customers&gt;
nJ: &lt;number_of_facilities&gt;
CapsJ: &lt;capacity_parameter&gt;
nIns: &lt;instance_index&gt;

CostJ: [(j) cost_j ...]
CapJ:  [(j) capacity_j ...]

CostIJ: [(i j) assignment_cost ...]
Pref:   [(i j) preference_rank ...]
</code></pre>

<h4>Meaning of the parameters</h4>

<ul>
  <li><code>CostJ[j]</code>: fixed cost of opening facility <code>j</code>.</li>
  <li><code>CapJ[j]</code>: capacity of facility <code>j</code>.</li>
  <li><code>CostIJ[i,j]</code>: cost of assigning customer <code>i</code> to facility <code>j</code>.</li>
  <li><code>Pref[i,j]</code>: position of facility <code>j</code> in the strict ranking of customer <code>i</code> (lower values indicate higher preference).</li>
</ul>

<h3>Instances in <code>instances/2/</code></h3>

<p>This folder contains the Calvete instances in their original format.</p>

<p>Each file includes the following data:</p>

<ul>
  <li><code>nJ</code>: number of facilities</li>
  <li><code>nI</code>: number of customers</li>
  <li><code>CostIJ</code>: assignment cost matrix</li>
  <li><code>demand</code>: customer demand vector</li>
  <li><code>CostJ</code>: facility opening cost vector</li>
  <li><code>CapJ</code>: facility capacity vector</li>
  <li><code>Pref</code>: customer preference information</li>
</ul>

<p>General structure:</p>

<pre><code>nJ: &lt;number_of_facilities&gt;
nI: &lt;number_of_customers&gt;

CostIJ:[ ... ]

demand:[ ... ]

CostJ:[ ... ]

CapJ:[ ... ]

Pref:[ ... ]
</code></pre>

<h4>Meaning of the parameters</h4>

<ul>
  <li><code>CostIJ</code>: assignment costs between facilities and customers.</li>
  <li><code>demand[i]</code>: demand of customer <code>i</code>.</li>
  <li><code>CostJ[j]</code>: fixed cost of opening facility <code>j</code>.</li>
  <li><code>CapJ[j]</code>: capacity of facility <code>j</code>.</li>
  <li><code>Pref</code>: preference information associated with customer-facility pairs.</li>
</ul>

<hr>

<h2>📄 Solution files</h2>

<p>The folder <code>solutions/</code> contains solution files in <code>.dat</code> format, one for each instance/model combination.</p>

<h3>Naming convention</h3>

<p>Solution files are named according to the stability concept and the instance. For example:</p>

<pre><code>SOL_WeaklyStable_Pro_Calvete_xcontinua_p_60.dat
</code></pre>

<p>This name indicates:</p>

<ul>
  <li><code>WeaklyStable</code>: the stability concept considered.</li>
  <li><code>p_60</code>: the instance identifier, in this case <code>P_60</code>.</li>
</ul>

<h3>Solution file structure</h3>

<p>Each solution file begins with two comment lines indicating the solved instance and the corresponding objective value:</p>

<pre><code># Instance: p_02.dat
# Objective value: 14404
</code></pre>

<p>Then the values of the decision variables are listed explicitly. A typical file may contain variables such as:</p>

<ul>
  <li><code>y[j]</code>: equals 1 if facility <code>j</code> is open, and 0 otherwise.</li>
  <li><code>x[i,j]</code>: equals 1 if customer <code>i</code> is assigned to facility <code>j</code>, and 0 otherwise.</li>
  <li>Auxiliary variables: additional variables introduced by the formulation.</li>
</ul>

<p>Example:</p>

<pre><code># Instance: p_02.dat
# Objective value: 14404
y[1] 1
y[2] 1
...
x[1,6] 1
...
</code></pre>

<p>These files provide the complete optimizer output for the corresponding instance, allowing the user to identify the selected facilities, customer assignments, and auxiliary decisions required by the formulation.</p>

<hr>

<h2>▶️ Using the models</h2>

<p>The Mosel files inside <code>models/</code> implement the stable formulations introduced in the article.</p>

<ol>
  <li>Open one of the <code>.mos</code> files in FICO Xpress Mosel.</li>
  <li>Select a <code>.dat</code> instance from the <code>instances/</code> folder.</li>
  <li>Execute the model to obtain the selected facilities, the customer allocation, and the objective value.</li>
  <li>Consult the corresponding file in <code>solutions/</code> to inspect the full solution associated with an instance.</li>
</ol>

<p>The repository includes formulations for the following stability concepts:</p>

<ul>
  <li>Weakly stable allocations</li>
  <li>Pairwise stable allocations</li>
  <li>Cyclic-coalition stable allocations</li>
</ul>

<hr>

<h2>📝 Citation</h2>

<pre><code>@article{dominguez2026stable,
  title   = {Stable formulations for the Capacitated Facility Location Problem with Customer Preferences},
  author  = {Domínguez, Concepción and Jaime-Alcántara, Juan de Dios},
  journal = {Preprint},
  year    = {2026}
}
</code></pre>

</html>
