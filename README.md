# Facility location with customer preferences — Supporting Dataset

This repository provides the supplementary dataset for the article on
facility location with customer preferences.

It contains the random `.dat` instances used in the computational
experiments reported in the paper, provided to ensure transparency
and reproducibility of the results.

---

## 📁 Instances

All data files are located in the folder `instances/`.

The instances follow the naming convention:

`CSPLPO_n_m_q_i.dat`

where:

- `n` is the number of plants,
- `m` is the number of customers,
- `q` is the plant capacity,
- `i` is the instance identifier.

For each combination of parameters `(n, m, q)`, five randomly generated
instances are included.

---

## 📄 Format of the `.dat` files

Each instance is provided in plain text format and can be directly used
within optimization models implemented in Mosel/Xpress.

The files contain the parameters defining the facility location problem,
including problem dimensions, costs, capacities, and preference-related
data as described in the article.

---

## 📝 Citation

If you use these instances, please cite the corresponding article:

```bibtex
@article{to_be_completed,
  title   = {Article title},
  author  = {Authors},
  journal = {Journal},
  year    = {Year}
}
