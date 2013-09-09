ohm-sorted
==========

[![Gem Version](https://badge.fury.io/rb/ohm-sorted.png)](http://badge.fury.io/rb/ohm-sorted)
[![Build Status](https://travis-ci.org/educabilia/ohm-sorted.png?branch=master)](https://travis-ci.org/educabilia/ohm-sorted)
[![Code Climate](https://codeclimate.com/github/educabilia/ohm-sorted.png)](https://codeclimate.com/github/educabilia/ohm-sorted)

Sorted indexes for Ohm


Setup
-----

1. Include the `Callbacks` and `Sorted` modules in your model:

		include Ohm::Callbacks 
		include Ohm::Sorted

2. Add a sorted index to your model with the following line:

		sorted :ranking, group_by: :status

You will need to resave every model if they already exist.

Usage
-----

To query the sorted index, use the `sorted_find` class method.

    >> Post.sorted_find(:ranking, status: "draft")


This returns an Ohm::SortedSet, which is just a subclass of Ohm::BasicSet
backed by a sorted set.


Requirements
------------

This plugin works with Ohm versions higher than 0.1.3.


Acknowledgements
----------------

Many thanks to Damian Janowski (https://github.com/djanowski)
