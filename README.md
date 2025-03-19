# vue

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar) (and disable Vetur).

## Type Support for `.vue` Imports in TS

Since TypeScript cannot handle type information for `.vue` imports, they are shimmed to be a generic Vue component type by default. In most cases this is fine if you don't really care about component prop types outside of templates.

However, if you wish to get actual prop types in `.vue` imports (for example to get props validation when using manual `h(...)` calls), you can run `Volar: Switch TS Plugin on/off` from VS Code command palette.

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
``

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

```
MyWallet
├─ .editorconfig
├─ .eslintrc-auto-import.json
├─ .eslintrc.cjs
├─ .npmrc
├─ .nvmrc
├─ .stylelintrc.json
├─ .vite
├─ README.md
├─ auto-imports.d.ts
├─ components.d.ts
├─ index.html
├─ jsconfig.json
├─ nginx.conf
├─ package.json
├─ pnpm-lock.yaml
├─ public
│  ├─ favicon.ico
│  ├─ images
│  │  ├─ avatars
│  │  │  ├─ avatar-1.png
│  │  │  └─ avatar-2.png
│  │  └─ svg
│  │     ├─ discord.svg
│  │     ├─ gift.svg
│  │     ├─ keyboard.svg
│  │     ├─ laptop.svg
│  │     ├─ lightbulb.svg
│  │     └─ rocket.svg
│  ├─ loader.css
│  └─ mockServiceWorker.js
├─ src
│  ├─ @core
│  │  ├─ components
│  │  │  ├─ AppBarSearch.vue
│  │  │  ├─ AppDrawerHeaderSection.vue
│  │  │  ├─ AppStepper.vue
│  │  │  ├─ CustomizerSection.vue
│  │  │  ├─ DialogCloseBtn.vue
│  │  │  ├─ DropZone.vue
│  │  │  ├─ I18n.vue
│  │  │  ├─ MoreBtn.vue
│  │  │  ├─ Notifications.vue
│  │  │  ├─ ProductDescriptionEditor.vue
│  │  │  ├─ ScrollToTop.vue
│  │  │  ├─ Shortcuts.vue
│  │  │  ├─ TablePagination.vue
│  │  │  ├─ TheCustomizer.vue
│  │  │  ├─ ThemeSwitcher.vue
│  │  │  ├─ TiptapEditor.vue
│  │  │  ├─ app-form-elements
│  │  │  │  ├─ AppDateTimePicker.vue
│  │  │  │  ├─ CustomCheckboxes.vue
│  │  │  │  ├─ CustomCheckboxesWithIcon.vue
│  │  │  │  ├─ CustomCheckboxesWithImage.vue
│  │  │  │  ├─ CustomRadios.vue
│  │  │  │  ├─ CustomRadiosWithIcon.vue
│  │  │  │  └─ CustomRadiosWithImage.vue
│  │  │  └─ cards
│  │  │     ├─ AppCardActions.vue
│  │  │     ├─ AppCardCode.vue
│  │  │     ├─ CardStatisticsHorizontal.vue
│  │  │     ├─ CardStatisticsVertical.vue
│  │  │     ├─ CardStatisticsWithIcon.vue
│  │  │     └─ CardStatisticsWithImages.vue
│  │  ├─ composable
│  │  │  ├─ createUrl.js
│  │  │  ├─ useCookie.js
│  │  │  ├─ useGenerateImageVariant.js
│  │  │  ├─ useResponsiveSidebar.js
│  │  │  └─ useSkins.js
│  │  ├─ enums.js
│  │  ├─ index.js
│  │  ├─ initCore.js
│  │  ├─ libs
│  │  │  ├─ apex-chart
│  │  │  │  └─ apexCharConfig.js
│  │  │  └─ chartjs
│  │  │     ├─ chartjsConfig.js
│  │  │     └─ components
│  │  │        ├─ BarChart.js
│  │  │        ├─ BubbleChart.js
│  │  │        ├─ DoughnutChart.js
│  │  │        ├─ LineChart.js
│  │  │        ├─ PolarAreaChart.js
│  │  │        ├─ RadarChart.js
│  │  │        └─ ScatterChart.js
│  │  ├─ scss
│  │  │  ├─ base
│  │  │  │  ├─ _components.scss
│  │  │  │  ├─ _dark.scss
│  │  │  │  ├─ _default-layout-w-horizontal-nav.scss
│  │  │  │  ├─ _default-layout-w-vertical-nav.scss
│  │  │  │  ├─ _default-layout.scss
│  │  │  │  ├─ _horizontal-nav.scss
│  │  │  │  ├─ _index.scss
│  │  │  │  ├─ _layouts.scss
│  │  │  │  ├─ _misc.scss
│  │  │  │  ├─ _mixins.scss
│  │  │  │  ├─ _route-transitions.scss
│  │  │  │  ├─ _utilities.scss
│  │  │  │  ├─ _utils.scss
│  │  │  │  ├─ _variables.scss
│  │  │  │  ├─ _vertical-nav.scss
│  │  │  │  ├─ libs
│  │  │  │  │  ├─ _perfect-scrollbar.scss
│  │  │  │  │  └─ vuetify
│  │  │  │  │     ├─ _index.scss
│  │  │  │  │     ├─ _overrides.scss
│  │  │  │  │     └─ _variables.scss
│  │  │  │  ├─ placeholders
│  │  │  │  │  ├─ _default-layout-horizontal-nav.scss
│  │  │  │  │  ├─ _default-layout-vertical-nav.scss
│  │  │  │  │  ├─ _default-layout.scss
│  │  │  │  │  ├─ _horizontal-nav.scss
│  │  │  │  │  ├─ _index.scss
│  │  │  │  │  ├─ _misc.scss
│  │  │  │  │  ├─ _nav.scss
│  │  │  │  │  └─ _vertical-nav.scss
│  │  │  │  └─ skins
│  │  │  │     ├─ _bordered.scss
│  │  │  │     └─ _index.scss
│  │  │  └─ template
│  │  │     ├─ _default-layout-w-horizontal-nav.scss
│  │  │     ├─ _default-layout-w-vertical-nav.scss
│  │  │     ├─ _utilities.scss
│  │  │     ├─ _utils.scss
│  │  │     ├─ _variables.scss
│  │  │     ├─ _vertical-nav.scss
│  │  │     ├─ index.scss
│  │  │     ├─ libs
│  │  │     │  ├─ apex-chart.scss
│  │  │     │  ├─ full-calendar.scss
│  │  │     │  ├─ shepherd.scss
│  │  │     │  ├─ swiper.scss
│  │  │     │  └─ vuetify
│  │  │     │     ├─ _overrides.scss
│  │  │     │     ├─ _variables.scss
│  │  │     │     ├─ components
│  │  │     │     │  ├─ _alert.scss
│  │  │     │     │  ├─ _avatar.scss
│  │  │     │     │  ├─ _badge.scss
│  │  │     │     │  ├─ _button.scss
│  │  │     │     │  ├─ _cards.scss
│  │  │     │     │  ├─ _checkbox.scss
│  │  │     │     │  ├─ _chip.scss
│  │  │     │     │  ├─ _dialog.scss
│  │  │     │     │  ├─ _expansion-panels.scss
│  │  │     │     │  ├─ _field.scss
│  │  │     │     │  ├─ _list.scss
│  │  │     │     │  ├─ _menu.scss
│  │  │     │     │  ├─ _otp-input.scss
│  │  │     │     │  ├─ _pagination.scss
│  │  │     │     │  ├─ _progress.scss
│  │  │     │     │  ├─ _radio.scss
│  │  │     │     │  ├─ _rating.scss
│  │  │     │     │  ├─ _slider.scss
│  │  │     │     │  ├─ _snackbar.scss
│  │  │     │     │  ├─ _switch.scss
│  │  │     │     │  ├─ _table.scss
│  │  │     │     │  ├─ _tabs.scss
│  │  │     │     │  ├─ _textarea.scss
│  │  │     │     │  ├─ _timeline.scss
│  │  │     │     │  ├─ _tooltip.scss
│  │  │     │     │  └─ index.scss
│  │  │     │     └─ index.scss
│  │  │     ├─ pages
│  │  │     │  ├─ misc.scss
│  │  │     │  └─ page-auth.scss
│  │  │     ├─ placeholders
│  │  │     │  ├─ _default-layout-horizontal-nav.scss
│  │  │     │  ├─ _default-layout-vertical-nav.scss
│  │  │     │  ├─ _horizontal-nav.scss
│  │  │     │  ├─ _index.scss
│  │  │     │  ├─ _misc.scss
│  │  │     │  ├─ _nav.scss
│  │  │     │  └─ _vertical-nav.scss
│  │  │     └─ skins
│  │  │        ├─ _bordered.scss
│  │  │        └─ _index.scss
│  │  ├─ stores
│  │  │  └─ config.js
│  │  ├─ types.js
│  │  └─ utils
│  │     ├─ colorConverter.js
│  │     ├─ formatters.js
│  │     ├─ helpers.js
│  │     ├─ plugins.js
│  │     ├─ validators.js
│  │     └─ vuetify.js
│  ├─ @layouts
│  │  ├─ components
│  │  │  ├─ HorizontalNav.vue
│  │  │  ├─ HorizontalNavGroup.vue
│  │  │  ├─ HorizontalNavLayout.vue
│  │  │  ├─ HorizontalNavLink.vue
│  │  │  ├─ HorizontalNavPopper.vue
│  │  │  ├─ TransitionExpand.vue
│  │  │  ├─ VNodeRenderer.jsx
│  │  │  ├─ VerticalNav.vue
│  │  │  ├─ VerticalNavGroup.vue
│  │  │  ├─ VerticalNavLayout.vue
│  │  │  ├─ VerticalNavLink.vue
│  │  │  └─ VerticalNavSectionTitle.vue
│  │  ├─ components.js
│  │  ├─ config.js
│  │  ├─ enums.js
│  │  ├─ index.js
│  │  ├─ plugins
│  │  │  └─ casl.js
│  │  ├─ stores
│  │  │  └─ config.js
│  │  ├─ styles
│  │  │  ├─ _classes.scss
│  │  │  ├─ _default-layout.scss
│  │  │  ├─ _global.scss
│  │  │  ├─ _mixins.scss
│  │  │  ├─ _placeholders.scss
│  │  │  ├─ _rtl.scss
│  │  │  ├─ _variables.scss
│  │  │  └─ index.scss
│  │  ├─ symbols.js
│  │  ├─ types.js
│  │  └─ utils.js
│  ├─ App.vue
│  ├─ assets
│  │  ├─ images
│  │  │  ├─ avatars
│  │  │  │  ├─ avatar-1.png
│  │  │  │  ├─ avatar-10.png
│  │  │  │  ├─ avatar-11.png
│  │  │  │  ├─ avatar-12.png
│  │  │  │  ├─ avatar-13.png
│  │  │  │  ├─ avatar-14.png
│  │  │  │  ├─ avatar-15.png
│  │  │  │  ├─ avatar-2.png
│  │  │  │  ├─ avatar-3.png
│  │  │  │  ├─ avatar-4.png
│  │  │  │  ├─ avatar-5.png
│  │  │  │  ├─ avatar-6.png
│  │  │  │  ├─ avatar-7.png
│  │  │  │  ├─ avatar-8.png
│  │  │  │  └─ avatar-9.png
│  │  │  ├─ customizer-icons
│  │  │  │  ├─ border-light.svg
│  │  │  │  ├─ collapsed-light.svg
│  │  │  │  ├─ compact-light.svg
│  │  │  │  ├─ default-light.svg
│  │  │  │  ├─ horizontal-dark.svg
│  │  │  │  ├─ horizontal-light.svg
│  │  │  │  ├─ ltr-light.svg
│  │  │  │  ├─ rtl-light.svg
│  │  │  │  └─ wide-light.svg
│  │  │  ├─ icons
│  │  │  │  ├─ brands
│  │  │  │  │  ├─ angular.png
│  │  │  │  │  ├─ asana.png
│  │  │  │  │  ├─ aws.png
│  │  │  │  │  ├─ behance.png
│  │  │  │  │  ├─ dribbble.png
│  │  │  │  │  ├─ facebook.png
│  │  │  │  │  ├─ firebase.png
│  │  │  │  │  ├─ github.png
│  │  │  │  │  ├─ google.png
│  │  │  │  │  ├─ instagram.png
│  │  │  │  │  ├─ laravel.png
│  │  │  │  │  ├─ linkedin.png
│  │  │  │  │  ├─ mailchimp.png
│  │  │  │  │  ├─ mysql.png
│  │  │  │  │  ├─ react.png
│  │  │  │  │  ├─ slack.png
│  │  │  │  │  ├─ twitter.png
│  │  │  │  │  └─ vue.png
│  │  │  │  ├─ countries
│  │  │  │  │  ├─ au.png
│  │  │  │  │  ├─ br.png
│  │  │  │  │  ├─ cn.png
│  │  │  │  │  ├─ fr.png
│  │  │  │  │  ├─ in.png
│  │  │  │  │  └─ us.png
│  │  │  │  ├─ file
│  │  │  │  │  ├─ txt.png
│  │  │  │  │  └─ xls.png
│  │  │  │  ├─ payments
│  │  │  │  │  ├─ american-express.png
│  │  │  │  │  ├─ img
│  │  │  │  │  │  ├─ ae-dark.png
│  │  │  │  │  │  ├─ american-express.png
│  │  │  │  │  │  ├─ dc-dark.png
│  │  │  │  │  │  ├─ dc-light.png
│  │  │  │  │  │  ├─ jcb-dark.png
│  │  │  │  │  │  ├─ jcb-light.png
│  │  │  │  │  │  ├─ master-dark.png
│  │  │  │  │  │  ├─ mastercard.png
│  │  │  │  │  │  ├─ paypal-dark.png
│  │  │  │  │  │  ├─ paypal-light.png
│  │  │  │  │  │  ├─ visa-dark.png
│  │  │  │  │  │  └─ visa-light.png
│  │  │  │  │  ├─ mastercard.png
│  │  │  │  │  └─ visa.png
│  │  │  │  └─ project-icons
│  │  │  │     ├─ calendar.png
│  │  │  │     ├─ event.png
│  │  │  │     ├─ figma.png
│  │  │  │     ├─ help.png
│  │  │  │     ├─ html5.png
│  │  │  │     ├─ image 6.png
│  │  │  │     ├─ marketing.png
│  │  │  │     ├─ pdf.png
│  │  │  │     ├─ python.png
│  │  │  │     ├─ react.png
│  │  │  │     ├─ sketch.png
│  │  │  │     ├─ social.png
│  │  │  │     ├─ support.png
│  │  │  │     ├─ twitter.png
│  │  │  │     ├─ vue.png
│  │  │  │     ├─ xamarin.png
│  │  │  │     └─ xd.png
│  │  │  ├─ logo.svg
│  │  │  ├─ logos
│  │  │  │  ├─ american-bank.png
│  │  │  │  ├─ aviato.png
│  │  │  │  ├─ aws.png
│  │  │  │  ├─ bitbank.png
│  │  │  │  ├─ chrome.png
│  │  │  │  ├─ citi-bank.png
│  │  │  │  ├─ digital-ocean.png
│  │  │  │  ├─ github.png
│  │  │  │  ├─ google.png
│  │  │  │  ├─ gumroad.png
│  │  │  │  ├─ mastercard-label.png
│  │  │  │  ├─ mastercard.png
│  │  │  │  ├─ paypal.png
│  │  │  │  ├─ slack.png
│  │  │  │  ├─ stripe.png
│  │  │  │  └─ zipcar.png
│  │  │  ├─ misc
│  │  │  │  ├─ Separator.png
│  │  │  │  ├─ fleet-car.png
│  │  │  │  ├─ misc-mask-dark.png
│  │  │  │  ├─ misc-mask-light.png
│  │  │  │  ├─ misc-under-maintenance.png
│  │  │  │  ├─ pricing-tree-1.png
│  │  │  │  ├─ pricing-tree-2.png
│  │  │  │  ├─ pricing-tree-3.png
│  │  │  │  ├─ tree1.png
│  │  │  │  ├─ tree2.png
│  │  │  │  ├─ tree3.png
│  │  │  │  ├─ triangle-dark.png
│  │  │  │  ├─ triangle-light.png
│  │  │  │  └─ trophy.png
│  │  │  ├─ pages
│  │  │  │  ├─ 1.png
│  │  │  │  ├─ 2.png
│  │  │  │  ├─ 3.png
│  │  │  │  ├─ 401.png
│  │  │  │  ├─ 404.png
│  │  │  │  ├─ 5.jpg
│  │  │  │  ├─ 6.jpg
│  │  │  │  ├─ TimelineRectangle1.png
│  │  │  │  ├─ TimelineRectangle2.png
│  │  │  │  ├─ TimelineRectangle3.png
│  │  │  │  ├─ TimelineRectangle4.png
│  │  │  │  ├─ academy-course-illustration1.png
│  │  │  │  ├─ academy-course-illustration2-dark.png
│  │  │  │  ├─ academy-course-illustration2-light.png
│  │  │  │  ├─ app-academy-tutor-1.png
│  │  │  │  ├─ app-academy-tutor-2.png
│  │  │  │  ├─ app-academy-tutor-3.png
│  │  │  │  ├─ app-academy-tutor-4.png
│  │  │  │  ├─ app-academy-tutor-5.png
│  │  │  │  ├─ app-academy-tutor-6.png
│  │  │  │  ├─ app-search-header-bg-dark.png
│  │  │  │  ├─ app-search-header-bg-light.png
│  │  │  │  ├─ auth-v2-forgot-password-illustration-dark-border.png
│  │  │  │  ├─ auth-v2-forgot-password-illustration-dark.png
│  │  │  │  ├─ auth-v2-forgot-password-illustration-light-border.png
│  │  │  │  ├─ auth-v2-forgot-password-illustration-light.png
│  │  │  │  ├─ auth-v2-login-illustration-bordered-dark.png
│  │  │  │  ├─ auth-v2-login-illustration-bordered-light.png
│  │  │  │  ├─ auth-v2-login-illustration-dark.png
│  │  │  │  ├─ auth-v2-login-illustration-light.png
│  │  │  │  ├─ auth-v2-register-illustration-bordered-dark.png
│  │  │  │  ├─ auth-v2-register-illustration-bordered-light.png
│  │  │  │  ├─ auth-v2-register-illustration-dark.png
│  │  │  │  ├─ auth-v2-register-illustration-light.png
│  │  │  │  ├─ auth-v2-reset-password-illustration-bordered-dark.png
│  │  │  │  ├─ auth-v2-reset-password-illustration-bordered-light.png
│  │  │  │  ├─ auth-v2-reset-password-illustration-dark.png
│  │  │  │  ├─ auth-v2-reset-password-illustration-light.png
│  │  │  │  ├─ auth-v2-two-steps-illustration-border-dark.png
│  │  │  │  ├─ auth-v2-two-steps-illustration-border-light.png
│  │  │  │  ├─ auth-v2-two-steps-illustration-dark.png
│  │  │  │  ├─ auth-v2-two-steps-illustration-light.png
│  │  │  │  ├─ auth-v2-verify-email-illustration-border-dark.png
│  │  │  │  ├─ auth-v2-verify-email-illustration-border-light.png
│  │  │  │  ├─ auth-v2-verify-email-illustration-dark.png
│  │  │  │  ├─ auth-v2-verify-email-illustration-light.png
│  │  │  │  ├─ background-1.jpg
│  │  │  │  ├─ background-2.jpg
│  │  │  │  ├─ background-3.jpg
│  │  │  │  ├─ boy-academy-illustration.png
│  │  │  │  ├─ boy-illustration.png
│  │  │  │  ├─ create-deal-review-complete.png
│  │  │  │  ├─ empty-cart.png
│  │  │  │  ├─ forgot-password-illustration.png
│  │  │  │  ├─ free-course-image1.png
│  │  │  │  ├─ free-course-image2.png
│  │  │  │  ├─ girl-academy-illustration.png
│  │  │  │  ├─ google-home.png
│  │  │  │  ├─ guitar-course.png
│  │  │  │  ├─ hero-bg.png
│  │  │  │  ├─ hero-dashboard-light.png
│  │  │  │  ├─ hero-elements-light.png
│  │  │  │  ├─ illustration-john.png
│  │  │  │  ├─ instructor-poster-image.png
│  │  │  │  ├─ iphone-11.png
│  │  │  │  ├─ mask-v2-dark.png
│  │  │  │  ├─ mask-v2-light.png
│  │  │  │  ├─ misc-coming-soon.png
│  │  │  │  ├─ page-not-found-illustration.png
│  │  │  │  ├─ pose-fs-9.png
│  │  │  │  ├─ pose_m1.png
│  │  │  │  ├─ puma-shoes.jpeg
│  │  │  │  ├─ register-multi-step-illustration.png
│  │  │  │  ├─ section-title-icon.png
│  │  │  │  ├─ shopping-girl.png
│  │  │  │  ├─ singing-course.png
│  │  │  │  ├─ teamPerson1.png
│  │  │  │  ├─ teamPerson2.png
│  │  │  │  ├─ teamPerson3.png
│  │  │  │  ├─ teamPerson4.png
│  │  │  │  ├─ themeselection-qr.png
│  │  │  │  ├─ tree-pot.png
│  │  │  │  └─ user-profile-header-bg.png
│  │  │  └─ svg
│  │  │     ├─ 3d-select-solid.svg
│  │  │     ├─ address.svg
│  │  │     ├─ cart.svg
│  │  │     ├─ check-circle.svg
│  │  │     ├─ check.svg
│  │  │     ├─ checkbox-checked.svg
│  │  │     ├─ checkbox-indeterminate.svg
│  │  │     ├─ checkbox-unchecked.svg
│  │  │     ├─ discord.svg
│  │  │     ├─ edit.svg
│  │  │     ├─ gift.svg
│  │  │     ├─ google-docs.svg
│  │  │     ├─ keyboard.svg
│  │  │     ├─ laptop-charging.svg
│  │  │     ├─ laptop.svg
│  │  │     ├─ layout-right.svg
│  │  │     ├─ lifebelt.svg
│  │  │     ├─ lightbulb.svg
│  │  │     ├─ list-arrow-icon.svg
│  │  │     ├─ medal.svg
│  │  │     ├─ paper-send.svg
│  │  │     ├─ payment.svg
│  │  │     ├─ paypal.svg
│  │  │     ├─ people-tag.svg
│  │  │     ├─ radio-checked.svg
│  │  │     ├─ radio-unchecked.svg
│  │  │     ├─ rocket.svg
│  │  │     ├─ stepper-check.svg
│  │  │     ├─ transition-up.svg
│  │  │     ├─ trending.svg
│  │  │     ├─ user-info.svg
│  │  │     ├─ vector.svg
│  │  │     ├─ wizard-account.svg
│  │  │     ├─ wizard-address.svg
│  │  │     ├─ wizard-personal.svg
│  │  │     ├─ wizard-social-link.svg
│  │  │     └─ wizard-submit.svg
│  │  └─ styles
│  │     ├─ styles.scss
│  │     └─ variables
│  │        ├─ _template.scss
│  │        └─ _vuetify.scss
│  ├─ components
│  │  ├─ AppLoadingIndicator.vue
│  │  ├─ AppSearchHeader.vue
│  │  ├─ ErrorHeader.vue
│  │  └─ dialogs
│  │     ├─ AddAuthenticatorAppDialog.vue
│  │     ├─ AddEditAddressDialog.vue
│  │     ├─ AddEditPermissionDialog.vue
│  │     ├─ AddEditRoleDialog.vue
│  │     ├─ AddPaymentMethodDialog.vue
│  │     ├─ CardAddEditDialog.vue
│  │     ├─ ConfirmDialog.vue
│  │     ├─ CreateAppDialog.vue
│  │     ├─ EnableOneTimePasswordDialog.vue
│  │     ├─ PaymentProvidersDialog.vue
│  │     ├─ PricingPlanDialog.vue
│  │     ├─ ReferAndEarnDialog.vue
│  │     ├─ ShareProjectDialog.vue
│  │     ├─ TwoFactorAuthDialog.vue
│  │     ├─ UserInfoEditDialog.vue
│  │     └─ UserUpgradePlanDialog.vue
│  ├─ composables
│  │  └─ useApi.js
│  ├─ layouts
│  │  ├─ blank.vue
│  │  ├─ components
│  │  │  ├─ DefaultLayoutWithHorizontalNav.vue
│  │  │  ├─ DefaultLayoutWithVerticalNav.vue
│  │  │  ├─ Footer.vue
│  │  │  ├─ NavBarNotifications.vue
│  │  │  ├─ NavSearchBar.vue
│  │  │  ├─ NavbarShortcuts.vue
│  │  │  ├─ NavbarThemeSwitcher.vue
│  │  │  └─ UserProfile.vue
│  │  └─ default.vue
│  ├─ main.js
│  ├─ navigation
│  │  ├─ horizontal
│  │  │  └─ index.js
│  │  └─ vertical
│  │     └─ index.js
│  ├─ pages
│  │  ├─ [...error].vue
│  │  ├─ apps
│  │  │  └─ user
│  │  │     ├─ list
│  │  │     │  └─ index.vue
│  │  │     └─ view
│  │  │        └─ [id].vue
│  │  ├─ dashboard.vue
│  │  ├─ index.vue
│  │  ├─ login.vue
│  │  └─ second-page.vue
│  ├─ plugins
│  │  ├─ 1.router
│  │  │  └─ index.js
│  │  ├─ 2.pinia.js
│  │  ├─ iconify
│  │  │  ├─ build-icons.js
│  │  │  ├─ icons.css
│  │  │  ├─ index.js
│  │  │  └─ package.json
│  │  ├─ layouts.js
│  │  ├─ vuetify
│  │  │  ├─ defaults.js
│  │  │  ├─ icons.js
│  │  │  ├─ index.js
│  │  │  └─ theme.js
│  │  └─ webfontloader.js
│  ├─ utils
│  │  ├─ api.js
│  │  ├─ constants.js
│  │  └─ paginationMeta.js
│  └─ views
│     ├─ apps
│     │  ├─ role
│     │  └─ user
│     │     ├─ list
│     │     │  └─ AddNewUserDrawer.vue
│     │     ├─ types.js
│     │     └─ view
│     │        ├─ UserBioPanel.vue
│     │        ├─ UserInvoiceTable.vue
│     │        ├─ UserTabBillingsPlans.vue
│     │        ├─ UserTabConnections.vue
│     │        ├─ UserTabNotifications.vue
│     │        ├─ UserTabOverview.vue
│     │        └─ UserTabSecurity.vue
│     ├─ dashboards
│     │  ├─ AnalyticsAward.vue
│     │  ├─ AnalyticsDepositWithdraw.vue
│     │  ├─ AnalyticsPerformance.vue
│     │  ├─ AnalyticsSalesByCountries.vue
│     │  ├─ AnalyticsSessionsBarCharts.vue
│     │  ├─ AnalyticsTotalEarning.vue
│     │  ├─ AnalyticsTotalProfit.vue
│     │  ├─ AnalyticsTransactions.vue
│     │  ├─ AnalyticsUserTable.vue
│     │  └─ AnalyticsWeeklyOverview.vue
│     └─ pages
│        └─ authentication
│           └─ AuthProvider.vue
├─ themeConfig.js
├─ typed-router.d.ts
└─ vite.config.js

```