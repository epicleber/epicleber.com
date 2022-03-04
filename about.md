---
layout: page
title: About
subtitle: 
use-site-title: true
---



<div class="container">
    	<div class="row">
            <div class="col-md-6">

Hi! I'm Cleber Vinicius Brito dos Santos. I'm a second-year doctorate student in Public Health at the <a href="https://www.ims.uerj.br">Instituto de Medicina Social"</a> at the State University of Rio de Janeiro (UERJ), under the joint supervision of <a href="https://scholar.google.com/citations?user=kVh9mCwAAAAJ&hl=pt-BR&oi=ao">Cláudio José Struchiner</a>, and <a href="https://scholar.google.com/citations?user=UK-Di5gAAAAJ&hl=pt-BR&oi=ao">Guilherme Loureiro Werneck</a>
In my master (at the same Institute and supervisors) I've studied the impact of deforestation in the occurrence of a neglected tropical disease, Visceral Leishmaniasis, through São Paulo State resulting in this <a href="https://royalsocietypublishing.org/doi/abs/10.1098/rspb.2021.1537">paper</a>.  
Previously, I finished a Bachelor's degree in Veterinary Medicine from the Universidade Federal Rural de Pernambuco and I went to an internship the Epidemiology sector of the Recife Health Secretariat during the 2015/2016 epidemic of dengue, Zika, and chikungunya.



  </p>
        
<div class="posts-list">
  {% for post in paginator.posts %}
  <article class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl }}">
	  <h2 class="post-title">{{ post.title }}</h2>

	  {% if post.subtitle %}
	  <h3 class="post-subtitle">
	    {{ post.subtitle }}
	  </h3>
	  {% endif %}
    </a>

    <p class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
    </p>

    <div class="post-entry-container">
      {% if post.image %}
      <div class="post-image">
        <a href="{{ post.url | prepend: site.baseurl }}">
          <img src="{{ post.image }}">
        </a>
      </div>
      {% endif %}
      <div class="post-entry">
        {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
        {% assign excerpt_word_count = post.excerpt | number_of_words %}
        {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
          <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</a>
        {% endif %}
      </div>
    </div>

    {% if post.tags.size > 0 %}
    <div class="blog-tags">
      Tags:
      {% if site.link-tags %}
      {% for tag in post.tags %}
      <a href="{{ site.baseurl }}/tag/{{ tag }}">{{ tag }}</a>
      {% endfor %}
      {% else %}
        {{ post.tags | join: ", " }}
      {% endif %}
    </div>
    {% endif %}

   </article>
  {% endfor %}
</div>

{% if paginator.total_pages > 1 %}
<ul class="pager main-pager">
  {% if paginator.previous_page %}
  <li class="previous">
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&larr; Newer Posts</a>
  </li>
  {% endif %}
  {% if paginator.next_page %}
  <li class="next">
    <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Older Posts &rarr;</a>
  </li>
  {% endif %}
</ul>
{% endif %}
