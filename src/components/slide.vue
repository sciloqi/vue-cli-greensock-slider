<script>

export default {
	name: 'slide',
	template: require('./page.html'),
	props: [
		'state'
	],
	methods: {
		enter(el, done) {
			const tl = new TimelineMax({
				onComplete: done
			})
			
			tl.set(el, {
				x: window.innerWidth * 1.5,
				scale: 0.8,
				transformOrigin: '50% 50%'
			})
			
			tl.to(el, 0.5, {
				x: 0,
				ease: Power4.easeOut
			});
			
			tl.to(el, 1, {
				scale: 1,
				ease: Power4.easeOut
			});
		},
		leave(el, done) {
			TweenMax.fromTo(el, 1, {
				autoAlpha: 1
			}, {
				autoAlpha: 0,
				ease: Power4.easeOut,
				onComplete: done
			});
		}	
	}
}
</script>

<style scoped></style>