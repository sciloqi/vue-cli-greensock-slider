<script>

export default {
	name: 'flipY',
	props: [
		'state'
	],
	template: require('./page.html'),
	methods: {
		enter(el, done) {
			const tl = new TimelineMax({
				onComplete: done
			})
			
			tl.set(el, {
				autoAlpha: 0,
				rotationY: 90,
				transformOrigin: '50% 50%'
			})
			
			tl.to(el, 1, {
				autoAlpha: 1,
				rotationY: 0,
				ease: Power4.easeOut
			})
		},
		leave(el, done) {
			TweenMax.to(el, 1, {
				scale: 0,
				ease: Power4.easeOut,
				onComplete: done
			});
		}	
	}
}
</script>

<style scoped></style>