<script lang="ts">
	import ModifyBelt from "$lib/components/admin/manage-students/modify/ModifyBelt.svelte";
import ModifyPoints from "$lib/components/admin/manage-students/modify/ModifyPoints.svelte";
	import ModifyStudentNumber from "$lib/components/admin/manage-students/modify/ModifyStudentNumber.svelte";

	export let data;
	$: ({ student } = data);
</script>

<section class="rounded-glass-container">
	<div>
		<h2>{student?.name}</h2>
		<h4>@{student?.username}</h4>
	</div>
	<span class="light-rounded-glass">
		<h4>{student?.points} Pts</h4>
		<ModifyPoints {data} username={student?.username || ""} currentPoints={student?.points || 0}></ModifyPoints>
	</span>
	<span class="light-rounded-glass">
		<h4>{student?.belt} Belt</h4>
		<ModifyBelt {data} username={student?.username || ""} currentBelt={student?.belt || ""}></ModifyBelt>
	</span>
	<span class="light-rounded-glass">
		<h4>Student Number: {student?.student_number}</h4>
		<ModifyStudentNumber {data} username={student?.username || ""} currentStudentNumber={student?.student_number || ""}></ModifyStudentNumber>
	</span>
	<span class="light-rounded-glass">
		<h4>Email: {student?.email}</h4>
		<!-- <button class="secondary-btn">Modify</button> -->
	</span>
	<span class="light-rounded-glass">
		<h4>Date of Birth: {new Date(`${student?.date_of_birth}`).toDateString()}</h4>
		<!-- <button class="secondary-btn">Modify</button> -->
	</span>
</section>

<style lang="scss">
	section {
		display: flex;
		gap: 1em;
		flex-direction: column;
		width: 100%;
		margin: 0 3em 2em;
		padding: 4em;

		h4 {
			font-family: 'Azo Sans';
		}
		div {
			display: flex;
			flex-direction: column;
			gap: 0.5em;
			margin: 1em 0;
		}
		span {
			display: flex;
			align-items: center;
			justify-content: space-between;
			width: 100%;
			padding: 1em;
		}
	}
</style>
