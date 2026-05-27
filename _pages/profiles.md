---
layout: page
title: Members
permalink: /members/
description: Meet our research group.
nav: true
nav_order: 2
---

<style>
  /* 1. STUDENT CARDS */
  .team-card-img {
    height: 250px;
    width: 100%; 
    object-fit: cover; 
  }
  
  /* 2. PI IMAGE FIX (Auto height to prevent cropping) */
  .pi-img {
    width: 100%;      
    height: auto;     
    max-height: 400px; 
    object-fit: cover; 
    border-radius: 4px 4px 0 0; 
  }



  /* Icons & Hover Effects */
  .linkedin-icon {
    color: #0077b5;
    text-decoration: none;
  }
  .linkedin-icon:hover {
    color: #005582;
    text-decoration: none;
  }

  .card:hover {
    box-shadow: 0 10px 20px rgba(0,0,0,0.1);
    transform: translateY(-2px);
    transition: all 0.3s ease-in-out;
  }
</style>

<div class="row mb-5">
  {% for member in site.data.team.pi %}
  <div class="col-sm-4">
    <div class="card border-0 z-depth-1">
      <img class="pi-img" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
    </div>
  </div>
  <div class="col-sm-8 mt-3 mt-sm-0">
    <h2 class="font-weight-bold">{{ member.name }}</h2>
    <h5 class="text-muted mb-3">{{ member.role }}</h5>
    <p>{{ member.bio }}</p>
    
    {% if member.url %}
    <a href="{{ member.url }}" class="btn btn-sm btn-outline-primary" target="_blank">
      <i class="fas fa-globe"></i> Website
    </a>
    {% endif %}
  </div>
  {% endfor %}
</div>

<hr>

<h3 class="mb-4 mt-4">PhD Students</h3>
<div class="row">
  {% for member in site.data.team.phd %}
  <div class="col-6 col-md-3 mb-4">
    <div class="card h-100 z-depth-1 border-0">
      <img class="card-img-top team-card-img" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
      <div class="card-body text-center p-2"> 
        <h5 class="card-title mb-1" style="font-size: 1.1rem;">{{ member.name }}</h5>
        <p class="card-text text-muted small mb-2">{{ member.role }}</p>
        
        {% if member.linkedin %}
        <a href="{{ member.linkedin }}" target="_blank" class="linkedin-icon">
          <i class="fab fa-linkedin fa-2x"></i>
        </a>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>

<h3 class="mb-4 mt-4">M.Tech Students</h3>
<div class="row">
  {% for member in site.data.team.mtech %}
  <div class="col-6 col-md-3 mb-4">
    <div class="card h-100 z-depth-1 border-0">
      <img class="card-img-top team-card-img" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
      <div class="card-body text-center p-2">
        <h5 class="card-title mb-1" style="font-size: 1.1rem;">{{ member.name }}</h5>
        <p class="card-text text-muted small mb-2">{{ member.role }}</p>
        
        {% if member.linkedin %}
        <a href="{{ member.linkedin }}" target="_blank" class="linkedin-icon">
          <i class="fab fa-linkedin fa-2x"></i>
        </a>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>


<h3 class="mb-4 mt-4">B.Tech Students</h3>
<div class="row">
  {% for member in site.data.team.btech %}
  <div class="col-6 col-md-3 mb-4">
    <div class="card h-100 z-depth-1 border-0">
      <img class="card-img-top team-card-img" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
      <div class="card-body text-center p-2">
        <h5 class="card-title mb-1" style="font-size: 1.1rem;">{{ member.name }}</h5>
        <p class="card-text text-muted small mb-2">{{ member.role }}</p>
        
        {% if member.linkedin %}
        <a href="{{ member.linkedin }}" target="_blank" class="linkedin-icon">
          <i class="fab fa-linkedin fa-2x"></i>
        </a>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>

<hr>

<hr>

<div class="d-flex align-items-center mb-4 mt-4">
  <h3 class="mb-0 mr-3">Alumni</h3>
  <button 
    class="btn btn-sm btn-outline-secondary alni-toggle-btn" 
    type="button" 
    data-toggle="collapse" 
    data-target="#alumniCollapse" 
    aria-expanded="false" 
    aria-controls="alumniCollapse"
  >
    <i class="fas fa-chevron-down mr-1"></i> Show / Hide Lab Alumni
  </button>
</div>

<div class="collapse" id="alumniCollapse">
  <div class="table-responsive">
    <table class="table table-hover border-0">
      <thead class="thead-light">
        <tr>
          <th scope="col">Name</th>
          <th scope="col">Course/Position</th>
          <th scope="col">Graduation Year</th>
          <th scope="col">Next / Current Affiliation</th>
        </tr>
      </thead>
      <tbody>
        {% for alumni in site.data.team.alumni %}
        <tr>
          <td>
            {% if alumni.linkedin or alumni.url %}
              <a href="{{ alumni.linkedin | default: alumni.url }}" target="_blank" style="font-weight: 500; text-decoration: none;">
                {{ alumni.name }} <i class="fab fa-linkedin fa-sm" style="margin-left: 4px; color: #0077b5;"></i>
              </a>
            {% else %}
              {{ alumni.name }}
            {% endif %}
          </td>
          
          <td>{{ alumni.role | default: alumni.course }}</td>
          
          <td>{{ alumni.year }}</td>
          
          <td>{{ alumni.affiliation }}</td>
        </tr>
        {% endfor %}
      </tbody>
    </table>
  </div>
</div>