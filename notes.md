---
title: Notes
header: Posts by Categories
permalink: /notes
---
<html>

  {% include head.html %}

<body class="index">

    {% include header.html %}
<div class="docs-header" id="content">
  <div class="container">
    <h1>Notes</h1>
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
        	<h1>Categories</h1>
          
      		<ul class="nav sidenav">
<!--
				{% if site.notes.first[0] == null %}
					{% for note in site.notes %}
				    	<li><a href="#{{ category }}-ref">
				    		{{  note | join: "/" }} <span style="color: #999999;" >({{ site.notes[note].size }})</span>
				    	</a></li>
			    	{% endfor %}
			  	{% else %}
			    	{% for category in site.categories %} 
				    	<li><a href="#{{ category[0] }}-ref">
				    		{{ category[0] | join: "/" }} <span style="color: #999999;" >({{ notes[1].size }})</span>
				    	</a></li>
			    	{% endfor %}
			  	{% endif %}
-->
          	</ul>
        </div>
          

      </div>
    </div>
    <div class="col-md-9" role="main">
      <div class="panel docs-content">
        <div class="wrapper">
          <div class="home">
			{% for note in site.notes %} 
			  <!--<h2 id="{{ category[0] }}-ref">{{ category[0] | join: "/" }}</h2>-->
			  <!--
        <ul>
			    {% assign pages_list = note %}  
			    {% include LessOrMore/pages_list %}
			  </ul>
        -->

        <li><a href="{{ note.url | prepend: site.baseurl }}">{{ note.title }}</a></li>        
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
