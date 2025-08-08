---
layout: page
title: Stuff
permalink: /stuff/
---

<style type="text/css">
.stuff-grid {
  /* margin-left: -100px; */
  /* margin-right: -300px; */
  display: grid;
  /* grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); */
  grid-template-columns: repeat(auto-fill, 200px);
  gap: 0.5rem;
  padding: 0rem;
  justify-content: start;
}

.stuff-box {
  display: block;
  border: 1px solid #dddddd;
  border-radius: 12px;
  padding: 0;
  text-decoration: none;
  transition: box-shadow 0.3s ease;
  /* transition: transform 0.3s ease; */
  height: 200px;
  width: 200px;
  position: relative;
  overflow: hidden;
  background-size: cover;
  background-position: center;
  background-color: transparent;
}

.stuff-box:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  /* transform: translateY(-2px); */
  text-decoration: none;
}

.stuff-topcontent {
    background: linear-gradient(
        to bottom,
        rgba(  255, 255, 255, 1.0) 0%,
        rgba(255, 255, 255, 0.8) 75%,
        rgba(255, 255, 255, 0.0) 100%
    );
    margin: 0;
    margin-bottom: 1.0rem;
    background-color: transparent;
    overflow: hidden;
    /* border-radius: 12px; */
    /* border-top-left-radius: 12px; */
    /* border-top-right-radius: 12px;    */
}

.stuff-content h2 {
  color: #000000;
  font-size: 1.1rem;
  margin-left: 0.5rem;
  margin-top: 0.1rem;
  /* backdrop-filter: blur(6px); */
}

.stuff-date {
  font-size: 0.8rem;
  color: #888888;
  margin-left: 0.5rem;
  margin-top: -0.9rem;
  /* backdrop-filter: blur(6px); */
}

.stuff-box:hover h2 {
  text-decoration: underline;
}

.stuff-tags {
  position: absolute;
  bottom: -0.5rem;
  left: 0.5rem;
  right: 0.25rem;
}

.tag {
  background:rgb(255, 255, 255, 0.8);
  color: #333333;
  /* border: 1px solid #dddddd; */
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
  font-size: 0.75rem;
}

.checkboxes {
  margin-bottom: 1rem;
}

.checkboxes label {
  margin-right: 1rem;
}

</style>


<div class=checkboxes>
{% for tag in site.tags %}
    <label>
      <input type="checkbox" class="tag-checkbox" value="{{ tag[0] }}">
      {{ tag[0] }}
    </label>
{% endfor %}
</div>


<div class="stuff-grid">
  {% for post in site.posts %}
    {% if post.link %}
        <a href="{{ post.link }}" class="stuff-box" style="background-image: url({{ post.image }});" data-tags="{{ post.tags | join: ',' }}" target="_blank">
    {% else %}
        <a href="{{ post.url }}" class="stuff-box" style="background-image: url({{ post.image }});" data-tags="{{ post.tags | join: ',' }}">
    {% endif %}
      <div class="stuff-content">
        <div class="stuff-topcontent">
            <h2 class="stuff-title">{{ post.title }} </h2>
            {% if post.nodate %}
                <!-- <p class="stuff-date"><div style="visibility: hidden;">_</div></p> -->
            {% else %}
                <p class="stuff-date">{{ post.date | date: "%Y-%m-%d" }}</p>
            {% endif %}
        </div>
        {% if post.tags %}
          <p class="stuff-tags">
            {% for tag in post.tags %}
              <span class="tag">{{ tag }}</span>
            {% endfor %}
          </p>
        {% endif %}
      </div>
    </a>
  {% endfor %}
</div>



<script>
  const checkboxes = document.querySelectorAll('.tag-checkbox');
  const posts = document.querySelectorAll('.stuff-box');

  function filterPosts() {
    const selectedTags = Array.from(checkboxes)
      .filter(cb => cb.checked)
      .map(cb => cb.value);

    posts.forEach(post => {
      const postCats = post.dataset.tags.split(',');
      // show post if it has at least one selected tag or if none selected show all
      if (selectedTags.length === 0 || selectedTags.some(cat => postCats.includes(cat))) {
        post.style.display = '';
      } else {
        post.style.display = 'none';
      }
    });
  }

  checkboxes.forEach(cb => cb.addEventListener('change', filterPosts));
  filterPosts();
</script>