---
layout: post
title:  Easy exact sensitivities for ocean CO<sub>2</sub> system
date: 2018-11-23 12:02:00+0100
description: New tools to help deconvolve controls of marine CO<sub>2</sub> variables
---

If you're a marine scientist attempting to deconvolve the contributions to
variations in CO<sub>2</sub> system variables, you should be very concerned
about how you compute the sensitivities of one variable to others.
Such deconvolution is often done by applying a first-order Taylor
series decomposition, but results don't always add up.

For example, with $$p\text{CO}_2 = f(\text{DIC}, \text{Alk}, T, S)$$,
i.e., neglecting contributions for dissolved inorganic phosphorus and
silicon, such a decomposition looks like

$$
\Delta p\text{CO}_2 = \frac{\partial p\text{CO}_2}{\partial \text{DIC}} \Delta \text{DIC}
            + \frac{\partial p\text{CO}_2}{\partial \text{Alk}} \Delta \text{Alk}
	    + \frac{\partial p\text{CO}_2}{\partial T} \Delta T
	    + \frac{\partial p\text{CO}_2}{\partial S} \Delta S
\text{.}
$$

That equation sums the contributions from the simultaneous change
($$\Delta$$) in each of the 4 input variables, with each $$\Delta$$
being multiplied by a partial derivative (sensitivity) so that each
term on the right has same units as the total change term on the left.

If results don't add up (i.e., the right side does not equal the
left), there are three potential causes: (1) the $$\Delta$$s are not
accurate enough, e.g., from imprecise measurements, (2) the
$$\Delta$$s are too large and the system is nonlinear, or (3) the
sensitivities are inaccurate.

In models, the first concern is not an issue because the $$\Delta$$s
are internally consistent.  The second concern might also be neglected
based on results from a recent model study.  [Kwiatkowski and Orr
(2018)](https://www.nature.com/articles/s41558-017-0054-0) deconvolved
modeled seasonal amplitudes of CO<sub>2</sub> system variables, i.e.,
where the $$\Delta$$s are typically quite large, but in all cases
their results added up precisely. Their success appears to stem from
the internal consistency and presumably the accuracy of their
calculated sensitivities, an issue that has not received enough
attention.

Sometimes sensitivities have been approximated by neglecting some
terms to get at a straightforward analytical approximation.  These
approximations are useful to help understand the system. But
their accuracy also matters when performing a Taylor series
decomposition because there is a delicate balance between terms in
some regions. Even minor imprecisions in the sensitivities of say 10%
can lead to things not adding up and thus to the wrong conclusions. So
if your deconvolution terms don't add up, stop and check your
sensitivities. Make sure that they are accurate.

Fortunately, it is now easy to avoid approximated sensitivities.
Accurate sensitivities are provided as part of the set of new routines that
were released along with the publication describing the
[OA-ICC](https://www.iaea.org/services/oa-icc)-funded effort to
provide uncertainty propagation add-ons in several public software packages
that compute CO<sub>2</sub> system variables [(Orr et al., 2018)](https://doi.org/10.1016/j.marchem.2018.10.006). These packages include
[CO2SYS-MATLAB](https://github.com/jamesorr/CO2SYS-MATLAB),
[seacarb](http://CRAN.R-project.org/package=seacarb), and
[mocsy](https://github.com/jamesorr/mocsy). Clicking on those links
will lead you directly to the archive where each package can be
downloaded, on CRAN for seacarb and on GitHub for the other 2
packages.

Each package includes a new routine called `derivnum` with a suffix that
depends on the computer language of each package (`.m`, `.R`, and
`.f90`). Input arguments are just like those for the preexisting routine
in each package that computes carbonate chemistry variables
(`CO2SYS.m`, `carb.R`, and `vars.f90`, respectively) except that there
is also one new argument added to the beginning of the list to specify
the variable with respect to which derivatives will be taken.

Besides the typical documentation for each package, the new archives
for CO2SYS-MATLAB, seacarb, and mocsy also contain a `notebooks`
directory, which itself contains `jupyter` notebook files with
extensive examples.  Jupyter has been highlighted in a recent [*Nature*
piece](https://www.nature.com/articles/d41586-018-07196-1) as the way
forward for scientists dealing with such data analysis. Once in that
`notebooks` directory, just click on the appropriately named notebook
file to visualize its contents as HTML. Even better, if you download a
package, those notebook files will be available locally; you may run
them interactively in your browser as `jupyter` notebooks.

More details about these routines are available in [Orr et
al. (2018)](https://doi.org/10.1016/j.marchem.2018.10.006).


REFERENCES

Kwiatkowski, L., and Orr, J. C. (2018) Diverging seasonal extremes for
ocean acidification during the twenty-first century, Nature Climate
Change 8, 2, 141-145,
[doi:10.1038/s41558-017-0054-0](https://www.nature.com/articles/s41558-017-0054-0).

Orr, J. C., Epitalon, J.-M., Dickson, A. G., and Gattuso, J.-P. (2018)
Routine uncertainty propagation for the marine carbon dioxide system,
*Mar. Chem. 207,* 84-107,
[doi:9.1016/j.marchem.2018.10.006](https://doi.org/10.1016/j.marchem.2018.10.006).

