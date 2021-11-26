## What is an Entity-Relationship Model (ER Model)?

Entity-relationship models are a graphical abstraction of data models.

They can be used to describe how different entities are related to each other. In other words: what their relationships are.

ER models can also be used to list all attributes of a given entity.

Creating an ER model is generally useful to get an idea of what kind of data is relevant for the situation and how it is related.

The situation and use case could be pretty much anything.

In terms of software development, ER models are a great way to illustrate data models for (relational) databases.

## Components
ER models have a strict set of shapes.

Each shape symbolizes an entity or an entity relation.

| # | Shape | Meaning
|---|---|---
|🟧| Rectangle | Entity
|🔶| Diamond | Realtionship
|🟠| Circle | Attribute

## Example
To get an idea of how to create an ER model and how to read en ER model, let us just create one.

![Example ER model](https://cdn.hashnode.com/res/hashnode/image/upload/v1637617887641/M2LIwK3Ep.jpeg?auto=compress)

This ER model includes three different entities:

1. Authors
2. Articles
3. Readers

Furthermore, we can read out of the ER model that the author and the reader both have names, where the article has a title and a date associated with it.

On top of the entities and their attributes, we can see how the different entities are connected to each other.

In fact, an author writes an article, or an article is written by an author and a reader reads that article, or this article is read by a reader.

And these are basically the core components of an ER model.

Feel free to check out the provided resources to dive even deeper into the topic.

## Resources
* [wikipedia.org](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model)
* [diagrameditor.com](https://www.diagrameditor.com)