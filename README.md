Welcome to the vj-accordion-steps wiki!
## What is Vj Accordion Steps?
This is a jQuery Plugin of Accordion as Steps with Individual Steps Validation and Optional Reset Steps in final step

## Features
* Validation/ Custom functions "Before/ After" Changing step.
* Changing respective step on clicking Title of step.
* Managing Steps Flow i.e Preventing "Next step" on trying before completing "Current step".
* Completed steps can be accessible by clicking on Title of step. Also, Custom Functions called on going to upper level step by clicking on step header. 

## How to use?
1. Including script
2. Html
3. Initiating Plugin

### 1. Including script
`<script src="//code.jquery.com/jquery-1.11.2.min.js"></script>`

`<script src="jquery-vj-accordion-steps.js"></script>`

### 2. Html

a. Html structure should have the id used for initializing **`<ul id="vj-steps-acc">`**

b. Each step should be enclosed inside (**`<li data-vjstepno="1">`**). Whereas data-vjstepno holds the step no. 

c. **`<h3>`** tag holds the title for the step.

d. **`<section>`** tag holds the content for respective step. 

_Example Html:_

       <ul id="vj-steps-acc" class="vjsteps_acc">
		<li data-vjstepno="1">
				<h3 class="vf-pr-step_heading">STEP 1</h3>
			<section>
				Content 1
				<span class="vjsteps_nxt vjbutton">Next</span>
			</section>
		</li>
		
		<li data-vjstepno="2">
			<h3 class="vf-pr-step_heading">STEP 2</h3>
			<section>
				Content 2
				<span class="vjbutton" onclick="$('#vj-steps-acc').vjaccordionsteps.reset_steps();">Finish</span>
			</section>
		</li>
     </ul>

### 3. Initiating Plugin

_Example Code:_

		<script>
			$('#vj-steps-acc').vjaccordionsteps({
				'vjacc_step_change_function': function(arr_params){
					return true;
				}, 
				'vjacc_after_step_change_function': function(arr_params){
					alert('Step changed.');
				}
			});
		</script>