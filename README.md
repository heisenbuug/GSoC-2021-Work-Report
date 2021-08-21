<p align="center">
  <img width="556" height="112" src="https://github.com/heisenbuug/GSoC-2021-Work-Report/blob/main/src/logo.png">
</p>

#### Organisation: [mlpack](https://github.com/mlpack)

#### Project: Replacing boost spirits

#### Mentor: [Omar Shrit](https://github.com/shrit)

## Abstract

This year my proposal got selected under GSoC-2021 by mlpack. `mlpack` is a fast, flexible and amazing C++ Machine Learning Library with awesome community. Over the years we have seen huge growth the application of ML. Doesn't matter for which application you are using ML, one thing that you will always need is Fast Data Loading.

## Overview of the project

The project revolves around reducing the binary footprint of mlpack by replacing the functionality of `boost::spirits` to handle a more diverse range of data in mlpack. This project is a part of the bigger goal of removing boost dependencies. The project aims to implement a parser by taking inspiration from armadillo's parser. A major goal will be to re-implement mlpack’s custom CSV parser that is currently being utilized to handle non-numeric data.

## Summary of Project

We were able to nearly acheive all the targets that were set in the proposal but there are many more things to do. We successfully implemented the parse for numeric data and also successfully removed `boost::spirit` and adapted the parse for non-numeric data as well.

### Here's my code

1. `load_csv.hpp` as base for the parser
    * Declarations of all the fucntions used for parsing.
    * Implementation of fucntions which are common to both types of parser.

2. `load_numeric_csv.hpp` for numeric parser
    * Functions for loading numeric data.

3. `load_categorical_csv.hpp` for cateforical data
    * Functions for loading categorical data using `DatasetMapper`.

4. Implemented `FileTyp` in mlpack to replace `arma::file_type`.

5. Implemented a set of string algorithms.
    * `trim()`
    * `trim_if()`

6. Example on how to use `DatasetMapper`

7. Adding `DatasetMapper` example to docs.

All of my work in wrapped in one PR only. You can have a look at the [PR](https://github.com/mlpack/mlpack/pull/2942).

Go through the PR to follow the discussions. You can also jump to [IRC](https://gitter.im/mlpack/mlpack). There are also mlpack [IRC logs](https://www.mlpack.org/irc/logs-all.html) which [Ryan](https://github.com/rcurtin) has worked very hard to maintain so you can have a look there as well.

 Best way to clear your querries? **Ping me!!!**. I would be more than happy to hear your views and clear any doubts that you have.
## Blog

I also logged my weekly progress and updates in form of blog. You can have a look [here](https://heisenbuug.github.io/).

## Future Scope

I will keep working on `mlpack` since I have realized that the best way to learn in to contribute. There is still soo much to do with the data loading part in mlpack. Once this is merged into the master I will start working on restructing the `load.hpp`. You can see more about it on my blog. I also have plans to work on creating a `DataFrame` class for mlpack.

## Note of Thanks

I would really like to thank `mlpack` for this awesome summer. My mentor [Omar Shrit](https://github.com/shrit) guided me at each and every step of the way. Not only my mentor but the whole community was very helpful. Thank you [Ryan](https://github.com/rcurtin), [Marcus](https://github.com/zoq) and everyone who were there for those aweomse discussions on IRC and weekly meetups.

At last I would like to thank Google for organising such an event and working towards the growth on open-source community.

























