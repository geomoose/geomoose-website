.. _rfc-8:

RFC 8: Updating linting rules
=============================

+---------------------+---------------+
| **Status:**         |               |
+---------------------+---------------+
| **Last Updated:**   | 2022-06-30    |
+---------------------+---------------+

+----------------+---------------------------+
| **Authors:**   | **Contact:**              |
+================+===========================+
| Dan Little     | GitHub: @theduckylittle   |
+----------------+---------------------------+

Overview and Scope
------------------

When the development of GeoMoose 3.x was started, JavaScript linting rules
were wildly varied among projects and highly opinionated. While the "eslint"
tool had provided some helpful standards for GeoMoose's homegrown style guide,
there are more consistent and modern linting rules and tools available.

Requirements
------------

1. Adopt `prettier<https://prettier.io/>`. Prettier is an opionionated code formatter
   that is used widely.
2. Adopt consistent rules and plugins for ESLint. Notably:

  * eslint:recommended
  * react/recommended
  * prettier/recommended

Impact
------

This will change the way the code looks and may not sit well with everyone's coding opinions.
However, by adopting and forcing the lint rules the code will be substantially more consistent.
This will make it more approachable by new developers and will make the code more readable over time.

Voting History
--------------

