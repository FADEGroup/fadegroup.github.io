---
layout: page
title: People
permalink: /people/
description: Meet our research group.
---

<style>
  /* Uniform Card Height & Image Crop */
  .team-card-img {
    height: 250px;
    object-fit: cover;
    width: 100%;
  }
  /* BTech Chip Avatar */
  .chip-img {
    width: 50px;
    height: 50px;
    object-fit: cover;
  }
  /* Hover effect for cards */
  .card:hover {
    box-shadow: 0 10px 20px rgba(0,0,0,0.1);
    transition: all 0.3s ease-in-out;
  }
</style>

<div class="row mb-5">
  {% for member in site.data.team.pi %}
  <div class="col-sm-4">
    <div class="card border-0 z-depth-1">
      <img class="card-img-top" src="{{ member.photo | relative_url }}" alt="{{ member.name }}" style="object-fit: cover; height: 300px;">
    </div>
  </div>
  <div class="col-sm-8 mt-3 mt-sm-0">
    <h2 class="font-weight-bold">{{ member.name }}</h2>
    <h5 class="text-muted mb-3">{{ member.role }}</h5>
    <p>{{ member.bio }}</p>
    {% if member.url %}
    <a href="{{ member.url }}" class="btn btn-sm btn-primary" target="_blank">Visit Website</a>
    {% endif %}
  </div>
  {% endfor %}
</div>

<hr>

<h3 class="mb-4 mt-4">PhD Scholars</h3>
<div class="row">
  {% for member in site.data.team.phd %}
  <div class="col-12 col-sm-6 col-md-3 mb-4">
    <div class="card h-100 z-depth-1 border-0">
      <img class="card-img-top team-card-img" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
      <div class="card-body text-center">
        <h5 class="card-title mb-1">{{ member.name }}</h5>
        <p class="card-text text-muted small">{{ member.role }}</p>
        {% if member.website %}
        <a href="{{ member.website }}" class="card-link small">Website</a>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>

<h3 class="mb-4 mt-4">Master's Students</h3>
<div class="row">
  {% for member in site.data.team.mtech %}
  <div class="col-12 col-sm-6 col-md-3 mb-4">
    <div class="card h-100 z-depth-1 border-0">
      <img class="card-img-top team-card-img" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
      <div class="card-body text-center">
        <h5 class="card-title mb-1">{{ member.name }}</h5>
        <p class="card-text text-muted small">{{ member.role }}</p>
      </div>
    </div>
  </div>
  {% endfor %}
</div>
      {% endfor %}
    </tbody>
  </table>
</div>