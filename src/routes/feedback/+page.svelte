<script>
	import FeedbackList from './FeedbackList.svelte';

	let primaryColor = 217;
	const toggleColor = () => (primaryColor *= 1.2);

	let feedback = [
		{
			id: 1,
			body: 'This is some awesome thinking!',
			rating: 100,
			user: {
				id: 63,
				username: 'eburras1q'
			}
		},
		{
			id: 2,
			body: 'What terrific math skills you’re showing!',
			rating: 27,
			user: {
				id: 71,
				username: 'omarsland1y'
			}
		},
		{
			id: 3,
			body: 'You are an amazing writer!',
			rating: 61,
			user: {
				id: 29,
				username: 'jissetts'
			}
		},
		{
			id: 4,
			body: 'Wow! You have improved so much!',
			rating: 8,
			user: {
				id: 19,
				username: 'bleveragei'
			}
		},
		{
			id: 5,
			body: 'Nice idea!',
			rating: 62,
			user: {
				id: 70,
				username: 'cmasurel1x'
			}
		},
		{
			id: 6,
			body: 'You are showing excellent understanding!',
			rating: 19,
			user: {
				id: 97,
				username: 'cdavydochkin2o'
			}
		},
		{
			id: 7,
			body: 'This is clear, concise, and complete!',
			rating: 47,
			user: {
				id: 22,
				username: 'froachel'
			}
		},
		{
			id: 8,
			body: 'What a powerful argument!',
			rating: 47,
			user: {
				id: 82,
				username: 'kogilvy29'
			}
		},
		{
			id: 9,
			body: 'I knew you could do it!',
			rating: 64,
			user: {
				id: 31,
				username: 'smargiottau'
			}
		},
		{
			id: 10,
			body: 'Wonderful ideas!',
			rating: 4,
			user: {
				id: 35,
				username: 'mbrooksbanky'
			}
		},
		{
			id: 11,
			body: 'It was a pleasure to grade this!',
			rating: 2,
			user: {
				id: 68,
				username: 'rstrettle1v'
			}
		},
		{
			id: 12,
			body: 'Keep up the incredible work!',
			rating: 50,
			user: {
				id: 77,
				username: 'rkingswood24'
			}
		},
		{
			id: 13,
			body: 'My goodness, how impressive!',
			rating: 37,
			user: {
				id: 28,
				username: 'xisherwoodr'
			}
		},
		{
			id: 14,
			body: 'You’re showing inventive ideas!',
			rating: 30,
			user: {
				id: 57,
				username: 'bpickering1k'
			}
		},
		{
			id: 15,
			body: 'You’ve shown so much growth!',
			rating: 44,
			user: {
				id: 76,
				username: 'cgaber23'
			}
		},
		{
			id: 16,
			body: 'Interesting thoughts!',
			rating: 71,
			user: {
				id: 100,
				username: 'pcumbes2r'
			}
		},
		{
			id: 17,
			body: 'I love your neat work!',
			rating: 68,
			user: {
				id: 37,
				username: 'nwytchard10'
			}
		},
		{
			id: 18,
			body: 'Doesn’t it feel good to do such great work?',
			rating: 41,
			user: {
				id: 31,
				username: 'smargiottau'
			}
		},
		{
			id: 19,
			body: 'First-rate work!',
			rating: 75,
			user: {
				id: 60,
				username: 'dlambarth1n'
			}
		},
		{
			id: 20,
			body: 'This is fascinating information!',
			rating: 48,
			user: {
				id: 17,
				username: 'vcholdcroftg'
			}
		},
		{
			id: 21,
			body: 'You inspire me!',
			rating: 29,
			user: {
				id: 5,
				username: 'kmeus4'
			}
		},
		{
			id: 22,
			body: 'This is right on target!',
			rating: 18,
			user: {
				id: 31,
				username: 'smargiottau'
			}
		},
		{
			id: 23,
			body: 'What an astounding observation!',
			rating: 73,
			user: {
				id: 14,
				username: 'mturleyd'
			}
		},
		{
			id: 24,
			body: 'This is very well thought out!',
			rating: 32,
			user: {
				id: 16,
				username: 'dpierrof'
			}
		},
		{
			id: 25,
			body: 'I can tell you’ve been practicing!',
			rating: 44,
			user: {
				id: 78,
				username: 'dbuist25'
			}
		},
		{
			id: 26,
			body: 'You’ve come a long way!',
			rating: 70,
			user: {
				id: 82,
				username: 'kogilvy29'
			}
		},
		{
			id: 27,
			body: 'I can tell you’ve been paying attention!',
			rating: 60,
			user: {
				id: 74,
				username: 'ahinckes21'
			}
		},
		{
			id: 28,
			body: 'Reading this made my day!',
			rating: 85,
			user: {
				id: 85,
				username: 'kpondjones2c'
			}
		},
		{
			id: 29,
			body: 'This is very perceptive!',
			rating: 13,
			user: {
				id: 30,
				username: 'kdulyt'
			}
		},
		{
			id: 30,
			body: 'What an accomplishment!',
			rating: 23,
			user: {
				id: 36,
				username: 'dalmondz'
			}
		}
	];

	const handleDeleteItem = (event) => {
		const itemId = event.detail;
		feedback = feedback.filter((item) => item.id !== itemId);
	};

	$: count = feedback.length;
</script>

<main>
	<div class="container">
		<h1 style="	color: hsl({primaryColor}, 100%, 40%);">Hi svelte form Nima</h1>
		<button on:click={toggleColor}>change the color</button>
		<h4>{count}</h4>
		<FeedbackList {feedback} on:deleteItem={handleDeleteItem} />
	</div>
</main>

<style>
	h1 {
		font-weight: bold;
	}
	h1:hover {
		text-decoration: underline;
	}
	button {
		padding: 1rem;
	}
</style>
