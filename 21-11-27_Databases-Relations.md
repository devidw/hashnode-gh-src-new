---
title: "1:1, 1:N, N:N ~ Database Relations"
slug: databases-relations
tags: database, databases, relation, relations
cover: https://david.wolf.gdn/media/cover.png
domain: xn--david-9u04d.to
date: 2021-11-27
lastmod: 2021-11-27
---

Entities in databases can have relationships with other entities.

These relationships are called **relations**.

In this article we will learn about the different types of relations.

Basically, a relation is a way to connect two entities.

There are three types of relations:

- One to one relations (1:1)
- One to many relations (1:n)
- Many to many relations (n:n)

## 1:1 Relations

If there is a unique relation between two entities, we call it a **1:1** relation.

### Examples

- Earth:Sun / Sun:Earth
  - The earth only has one sun.
  - The sun only has one earth.

## 1:N Relations

We speak of **1:N** relations when there is a relation between one entity and many other entities.

### Examples

- Student:Course / Course:Student
  - One student can have many courses.
  - And one course can have many students.

## N:N Relations

If there are many relations between two entities in both directions, we call it a **N:N** relation.

Since **N:N** relations are not unique, they are not valid in databases. Rather they have to be split into 1:N and 1:1 relations by using additional tables.

## Examples

- Teacher:Student / Student:Teacher
  - One teacher can have many students.
  - And one student can have many teachers.
