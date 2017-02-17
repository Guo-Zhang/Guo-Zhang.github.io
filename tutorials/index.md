---
title: Tutorials
header: Posts by Courses
---
<html>

  {% include head.html %}

<body class="index">

    {% include header.html %}
<div class="docs-header" id="content">
  <div class="container">
    <h1>Tutorials</h1>
      <p>{{ page.header }}</p>
      </div>
    </div>


<div class="container docs-container">
  <div class="col-md-9" role="main">

<div class="container docs-container">
  <div class="row">
    <div class="col-md-3">
      <div class="sidebar hidden-print" role="complementary">
        <div id="navigation">
        	<h1>Courses</h1>
      		<ul class="nav sidenav">
				{% if site.courses.first[0] == null %}
					{% for course in site.courses %} 
				    	<li><a href="#{{ course }}-ref">
				    		{{ course | join: "/" }} <span style="color: #999999;" >({{ site.courses[course].size }})</span>
				    	</a></li>
			    	{% endfor %}
			  	{% else %}
			    	{% for course in site.courses %} 
				    	<li><a href="#{{ course[0] }}-ref">
				    		{{ course[0] | join: "/" }} <span style="color: #999999;" >({{ course[1].size }})</span>
				    	</a></li>
			    	{% endfor %}
			  	{% endif %}
          	</ul>
        </div>
      </div>
    </div>
    <div class="col-md-9" role="main">
      <div class="panel docs-content">
        <div class="wrapper">
          <div class="home">
			{% for course in site.courses %} 
			  <h2 id="{{ course[0] }}-ref">{{ course[0] | join: "/" }}</h2>
			  <ul>
			    {% assign pages_list = course[1] %}  
			    {% include LessOrMore/pages_list %}
			  </ul>
			{% endfor %}
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

    </div>

</div>

    
    {% include footer.html %}

  </body>
</html>
