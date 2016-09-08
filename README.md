  Usually,I just use the underscore as a template engine.Which means most of code of underscore is superfluous to me.
To make the web page as light as possible,I extract the code of template engine of underscore;
   <br><br><strong>Using it follow these steps</strong>
   1. Include the js file \<script src="template.js">\</script>
   2. Write the template like a string in the js  like :<br>
   var templateStr = \` <br>
		<% _.each(datas, function (item) { %><br>
  			\<div class="outer"><br>
  		 	 <%= item.title %> - <%= item.url %> - <%= item.film %><br>
 			 \</div><br>
		 <% }); %><br>
		<% if(datas.length>3) {%><br>
			\<p> datas's length is more than 3 \</p><br>
		<%}%><br>
		\`;<br>
   Or write the template in a script element which type is template and get it by 
   element's innerHTML;Such as follow:
   \<script type="text/template" id="myTpl"><br>
		  <% _.each(datas, function (item) { %><br>
  			\<div class="outer"><br>
  		 	 <%= item.title %> - <%= item.url %> - <%= item.film %><br>
 			 \</div><br>
		 <% }); %><br>
		<% if(datas.length>3) {%><br>
			\<p> datas's length is more than 3 \</p><br>
		<%}%><br>
		\</script><br>
		\<script><br>
		var templateStr = document.getElementById("myTpl").innerHTML;<br>
		\</script><br>`
   3.  Parse the template string to a html string use function _.template.Like var html = _.template(templateStr)(datas).
   4. Render the html :document.body.innerHTML = html;
		
<strong>Something about underscore tempate</strong><br>
   <%  %> - to execute some code<br>
   <%= %> - to print some value in template<br>
   <%- %> - to print some values HTML escaped<br>
   logic judgment: <% if(conditions) {%> express <% }else{ %> express <% } %><br>
   iterate an array: <% _.each(array,function(item){ %> <element><%= item %></element> <% } %><br>
   
   
   
  
