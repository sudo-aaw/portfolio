<script lang="ts">
	import EducationBlock from '$lib/components/CareerBlocks/EducationBlock.svelte';
	import EducationTimeline from '$lib/components/CareerBlocks/EducationTimeline.svelte';
</script>

<div id="page" class="align-center flex h-screen items-center mt-0">
	<div class="flex flex-col h-screen">
		<EducationTimeline>
			<EducationBlock
				educationLevel="Bachelors of Computer Science with Honours"
				schoolName="University of Lancaster"
				dates="September 2019-September 2021"
				points={['First Class', '80% Dissertation Grade']}
				morePoints={[
					'Part of the collegiate debating team, winning the inter-college debating competition',
					'Completed my dissertation titled where I explored the use of computers as dialogic readers to enable children without an adult to read with to read with the conversational agent instead. This project included a prototype and longitudinal study acheiveing 80%'
				]}
			/>

			<EducationBlock
				educationLevel="A-Level"
				schoolName="Bolton School Boys' Division Sixth Form for boys"
				dates="September 2017-September 2019"
				points={['B - Mathematics', 'B - Physics', 'B - Design Engineering']}
				morePoints={[
					'Won half-colours for my efforts in the debating society, an award for students who shown dedication in public speaking and debating',
					'Built a smart-coaster for dementia patients that tracks water usage based on weight detection',
					'DofE Bronze'
				]}
			/>

			<EducationBlock
				educationLevel="GCSE"
				schoolName="Bolton School Boys' Division High School for boys"
				dates="September 2012-September 2017"
				points={['10 - A* to B including Mathematics and English']}
				morePoints={[
					'A* - Biology',
					'A* - Physics',
					'A* - Chemistry',
					'A - English Literature',
					'A - Mathematics',
					'A - Design & Technology',
					'A - Geography',
					'B - English language',
					'B - History',
					'B - French'
				]}
			/>
		</EducationTimeline>
	</div>
</div>

<style>
	#page {
		background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
		background-size: 400% 400%;
		animation: gradient 15s ease infinite;
		height: 100vh;
	}

	@keyframes gradient {
		0% {
			background-position: 0% 50%;
		}
		50% {
			background-position: 100% 50%;
		}
		100% {
			background-position: 0% 50%;
		}
	}
</style>
