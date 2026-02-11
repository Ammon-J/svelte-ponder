<script>
	let { post } = $props();
</script>

<section>
	<h2>{post.title}</h2>
	<ul>
		{#each post.tags as tag}
				<li>{tag}</li>
		{/each}
	</ul>
	<p>{post.body}</p>
	<br />
</section>

<style>
ul {
  text-align: center;   /* Center the text inside the list */
  width: 100%;          /* Full width of the container */
  list-style: none;      /* Remove default bullets */
  padding: 0;            /* Remove default padding */
  margin: 0;             /* Remove default margin */
  display: flex;         /* Use Flexbox for layout */
  flex-wrap: wrap;       /* Allow tags to wrap to the next line */
  gap: 10px;             /* Space between tags */
}

/* 2. Style the individual items (The Cards) */
ul li {
  text-align: center;   /* Center the text inside the list */
  background-color: #e0e7ff; /* Light blue background */
  color: #3730a3;            /* Dark blue text */
  padding: 8px 16px;         /* Top/Bottom, Left/Right padding */
  border-radius: 50px;       /* Makes the edges fully rounded (Pill shape) */
  font-family: sans-serif;   /* Clean font */
  font-size: 14px;
  font-weight: 600;          /* Slightly bold text */
  
  /* Optional: Add a subtle shadow for depth */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  
  /* Smooth transition for hover effects */
  transition: all 0.3s ease;
  cursor: default;           /* Or 'pointer' if they are clickable links */
}

/* 3. Add a Hover Effect */
ul li:hover {
  background-color: #3730a3; /* Invert colors on hover */
  color: #ffffff;
  transform: translateY(-2px); /* Slight lift effect */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Stronger shadow */
}
</style>