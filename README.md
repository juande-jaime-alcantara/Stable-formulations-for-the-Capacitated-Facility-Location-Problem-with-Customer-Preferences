<!DOCTYPE html>
<html lang="en">

<h1>Stable formulations for the Capacitated Facility Location Problem with Customer Preferences — Supporting Material</h1>

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
models/
README.md
</code></pre>

<ul>
  <li><code>instances/</code>: Randomly generated instances used in the computational experiments of the article.</li>
  <li><code>models/</code>: Mosel/Xpress model files implementing the MILP formulations presented in the paper.</li>
  <li><code>README.md</code>: Description of the repository structure, instance format and usage instructions.</li>
</ul>

<hr>

<h2>📄 Instance format and naming</h2>

<p>Each instance follows the naming format:</p>

<pre><code>CSPLPO_n_m_q_s.dat
</code></pre>

<h3>Naming convention</h3>

<ul>
  <li><code>n</code>: number of customers</li>
  <li><code>m</code>: number of plants (facilities)</li>
  <li><code>q</code>: capacity assigned to each plant</li>
  <li><code>s</code>: instance index (five instances are provided for each parameter tuple)</li>
</ul>

<p>Example:</p>

<pre><code>CSPLPO_50_5_12_1.dat
</code></pre>

<h3>File structure</h3>

<p>Each instance is provided in plain text format and contains:</p>

<ul>
  <li><code>nI</code>: number of customers</li>
  <li><code>nJ</code>: number of plants</li>
  <li><code>CapsJ</code>: common capacity parameter used in the generation</li>
  <li><code>nIns</code>: instance index</li>
  <li><code>CostJ</code>: opening cost of each plant</li>
  <li><code>CapJ</code>: vector of plant capacities</li>
  <li><code>CostIJ</code>: assignment cost matrix</li>
  <li><code>Pref</code>: strict preference ranking of plants for each customer</li>
</ul>

<p>General structure:</p>

<pre><code>nI: &lt;number_of_customers&gt;
nJ: &lt;number_of_plants&gt;
CapsJ: &lt;capacity_parameter&gt;
nIns: &lt;instance_index&gt;

CostJ: [(j) cost_j ...]
CapJ:  [(j) capacity_j ...]

CostIJ: [(i j) assignment_cost ...]
Pref:   [(i j) preference_rank ...]
</code></pre>

<h3>Meaning of the parameters</h3>

<ul>
  <li><code>CostJ[j]</code>: fixed cost of opening plant j.</li>
  <li><code>CapJ[j]</code>: capacity of plant j (all entries equal to <code>CapsJ</code>).</li>
  <li><code>CostIJ[i j]</code>: cost of assigning customer i to plant j.</li>
  <li><code>Pref[i j]</code>: position of plant j in the strict ranking of customer i (lower values indicate higher preference).</li>
</ul>

<hr>

<h2>▶️ Using the models</h2>

<p>The Mosel files inside <code>Models/</code> implement the stable formulations introduced in the article.</p>

<ol>
  <li>Open one of the <code>.mos</code> files in FICO Xpress Mosel.</li>
  <li>Select a <code>.dat</code> instance from the <code>Instances/</code> folder.</li>
  <li>Execute the model to obtain the selected facilities, the allocation of customers and the objective value.</li>
</ol>

<p>Each stability concept is studied through two formulations: an initial formulation and an improved (Pro) formulation.</p>

<ul>
  <li>Customer stable allocations</li>
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
