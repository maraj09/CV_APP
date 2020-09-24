<template>
	<div>
		<!-- Home Start  -----------------------------------------------------------
		----------------------------------------------------------------------->
		<section class="panel b-blue" id="1">
			<article class="panel__wrapper">
				<div class="panel__content  " :class="{  'panel__content--active' : isLoad }" >
					<div class="container">
						<div class="row">
							<div class="col-md-12 ">
								<div class="home-content">
									<div class="home-heading">
										<h1><em>Stak</em> HTML CSS</h1>
									</div>
									<div class="row">
										<div class="col-md-12">
											<div class="home-box-content">
												<div class="left-text">
													<h4>
														New
														<em>Stacked</em>
														Template
													</h4>
													<p>
														Stacked HTML CSS
														Template is provided by
														TemplateMo website. You
														can edit and use this
														template for any
														purpose. Please mention
														your friends about our
														website. Thank you.
													</p>
													<div class="primary-button">
														<a href="#2"
															>Discover More</a
														>
													</div>
												</div>
												<div class="right-image">
													<img
														src="img/right-home-image.png"
														alt=""
													/>
												</div>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</article>
		</section>
		<!-- Home End  -----------------------------------------------------------
		----------------------------------------------------------------------->
		
	</div>
</template>

<script>
export default {
	data() {
		return {
			isLoad : false
		}
	},
	methods: {
		onWindowLoad() {
			this.isLoad = true
		}
	},
	mounted () {
		window.addEventListener("load", this.onWindowLoad);
	},
};
</script>

<style lang="scss" scoped></style>
