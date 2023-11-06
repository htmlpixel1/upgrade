<template>
	<div v-if="isLogin && withdrowAnalogItemData" id="withdrawAnalog" class="modal-window widthdrow-modal">
		<div class="styles_w__modal__6sdLu styles_color--light__vheAu styles_size--m__iYDvT">
			<div class="styles_modal__overlay__N_SvY"></div>
			<div class="styles_modal_scroll__container__coD3X">
				<div class="styles_modalContainer__kwb9D">
					<div class="styles_modal__RtAXJ">
						<div class="styles_winter__uoHSX"></div>
						<div class="styles_container__content__w_91X">
							<div class="styles_modalContainerHeader__2tU6Z">
								<div class="styles_modalTitle__9FRvf">
									<div class="styles_modal__title__sH9y3"><svg width="24" height="24" viewBox="0 0 24 24" fill="none"
											class="styles_icon__gfIyj styles_variant--h3__6pwB_">
											<path
												d="M15.429 10.073v-4.48c0-.379-.356-.687-.794-.687h-6.95V2.689c0-.607-.845-.917-1.347-.493L.24 7.34a.626.626 0 000 .985l6.098 5.145c.502.423 1.348.115 1.348-.493V10.76h6.949c.438 0 .794-.308.794-.688zm8.331 5.601l-6.098-5.145c-.502-.423-1.348-.115-1.348.493v2.217H9.365c-.438 0-.794.308-.794.688v4.48c0 .38.356.688.794.688h6.95v2.217c0 .609.848.914 1.347.493l6.098-5.145a.626.626 0 000-.986z"
												fill="var(--color-white)"></path>
										</svg>
										<div
											class="styles_text__1p2r2 styles_color--white__8knwn styles_variant--h5__u0ttf styles_bold__2c_3x styles_uppercase__3jJx7">
											Замена скина</div>
										<div v-if="withdrowAnalogItemData.balance > 0" class="styles_moneyback__container__4d6cN">
											<div
												class="styles_text__1p2r2 styles_color--green__d3Y0w styles_variant--h6__GhwNM styles_bold__2c_3x">
												Вернем на баланс {{ withdrowAnalogItemData.balance }} ₽</div>
										</div>
									</div>
								</div><button class="styles_modalClose__OsL5G"><svg width="24" height="24" viewBox="0 0 24 24" fill="none"
										class="styles_icon__gfIyj styles_variant--h6__ZzEoJ">
										<g clip-path="url(#close_svg__close_svg__clip0_8402_11181)">
											<path fill-rule="evenodd" clip-rule="evenodd"
												d="M14.55 12l8.921 8.922a1.803 1.803 0 01-2.549 2.55L12 14.549l-8.923 8.923a1.803 1.803 0 01-2.549-2.55L9.451 12 .528 3.077A1.803 1.803 0 013.078.528L12 9.451 20.922.528a1.803 1.803 0 012.55 2.55L14.549 12z"
												fill="var(--color-secondary-text)"></path>
										</g>
										<defs>
											<clipPath id="close_svg__close_svg__clip0_8402_11181">
												<path fill="#fff" d="M0 0h24v24H0z"></path>
											</clipPath>
										</defs>
									</svg></button>
							</div>
							<div class="styles_modalContainerBody__TB_7n">
								<div class="styles_modal__content__FUyo9">
									<div class="styles_skinReplace__body__vGbIt">
										<div class="styles_body__scroll__hkZyI">
											<div class="styles_skinReplace__list__S194_"><button
													class="styles_list__item__VNcn6 styles_rarity--0__0aEIo" aria-disabled="false">
													<div class="styles_item__count__Cw3Km">1</div>
													<div class="styles_skin__container__f0kAx styles_rarity--0__KxH_n styles_size--medium__6jrca"
														:class="withdrowAnalogItemData.analog.rarity">
														<div class="styles_skinCard__BswD3">
															<div class="styles_skinCard__price__0Ic6x">
																<div
																	class="styles_text__1p2r2 styles_color--green__d3Y0w styles_variant--h6__GhwNM styles_bold__2c_3x">
																	{{ withdrowAnalogItemData.analog.price }} ₽</div>
															</div>
															<div class="styles_skinCard__image_wrapper__Pmazs"><img
																	:src="withdrowAnalogItemData.analog.image" :alt="withdrowAnalogItemData.analog.name"
																	class="styles_skinCard__image__Lp6F6" loading="lazy" decoding="async"></div>
															<div class="styles_skinCard__backdrop__3CBDr">
																<div class="styles_skinIcon__background__vVqr9 styles_rarity--0__NoJMV"></div>
															</div>
															<div class="styles_skinCard__footer___3yR6">
																<div class="styles_skinCard__footer_left_side___qg5w">
																	<div class="styles_drops__names___ZKan">
																		<div class="styles_name__bottom__Z63oy"><span
																				class="styles_text__1p2r2 styles_color--inherit__x13rS styles_variant--h6__GhwNM styles_bold__2c_3x styles_noWrap__kn3Uq"
																				v-html="statTrackName(withdrowAnalogItemData.analog.name)">
																			</span></div>
																	</div>
																</div>
															</div>
														</div>
														<div class="styles_skinCard__backdrop__d8nFB">
															<div class="styles_skinIcon__background__vVqr9 styles_rarity--0__NoJMV"></div>
														</div>
														<div class="styles_skinCard__divider__z4Xe_ styles_rarity--0__KxH_n"></div>
													</div>
												</button></div>
										</div>
									</div>
									<div class="styles_footer__controls__rK0kO"><button @click="withdrawItem"
											class="styles_control__ZeUvc styles_color--gold__0mj1h styles_size--medium__XtJLC styles_full-width__9ENOQ styles_button__wKrkP"
											type="button">
											<div class="styles_button__content__1KVfc">
												<div
													class="styles_text__1p2r2 styles_color--inherit__x13rS styles_variant--h5__u0ttf styles_bold__2c_3x styles_uppercase__3jJx7">
													Заменить</div>
											</div>
										</button><button @click="close"
											class="styles_control__ZeUvc styles_color--gray-primary__6lJWk styles_size--medium__XtJLC styles_full-width__9ENOQ styles_button__wKrkP"
											type="button">
											<div class="styles_button__content__1KVfc">
												<div
													class="styles_text__1p2r2 styles_color--inherit__x13rS styles_variant--h5__u0ttf styles_bold__2c_3x styles_uppercase__3jJx7">
													Отменить</div>
											</div>
										</button></div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
export default {
	props: {
		withdrowAnalogItemData: false
	},
	data: () => ({
		itemActionInProgress: false
	}),
	mounted() {
		$(document).on('click', '#withdrawAnalog', () => {
			return false;
		});
		$(document).on('click', 'body', () => {
			this.$emit('closeWithdrawAnalogModal');
			return false;
		});
	},
	beforeDestroy() {
		$(document).off('click', '#withdrawAnalog');
		$(document).off('click', 'body');
	},
	methods: {
		close() {
			this.$emit('closeWithdrawAnalogModal');
		},
		statTrackName(name) {
			return name.replace('StatTrak™', '<span class = "stattrak-color">StatTrak™</span>');
		},
		withdrawItem() {
			let item = this.withdrowAnalogItemData.item;
			if (this.itemActionInProgress || item.disable) {
				return;
			}
			this.itemActionInProgress = true;
			this.$set(item, 'disable', true);
			let balance = this.withdrowAnalogItemData.balance;
			Utils.apiPostCall("/api/opencase/withdraw/analogs/" + item.id + "/", { analog: this.withdrowAnalogItemData.analog.id })
				.then(resp => {
					if (resp.data.success) {
						item.status = 1;
						if (balance > 0) {
							this.$store.commit('changeBalance', balance);
						}
						Utils.userAlert(resp.data.msg, '', 'success');
					} else {
						Utils.userAlert('Возникла ошибка при отправке предмета', resp.data.error, 'warn');
					}
					this.itemActionInProgress = false;
					this.$set(item, 'disable', false);
				})
				.catch(err => {
					this.itemActionInProgress = false;
					this.$set(item, 'disable', false);
					Utils.userAlert('Возникла ошибка при отправке предмета', err.response.statusText, 'error');
				});
			this.close();
		}
	},
	computed: {
		isLogin() {
			return this.$store.getters.isLogin;
		}
	}
}
</script>