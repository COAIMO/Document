---
description: 리액터를 이용한 PWA(Progressive Web App) 개발 가이드
---

# React PWA 개발

## PWA란?

PWA는 웹과 네이티브 앱의 기능 모두의 이점을 갖도록 수 많은 특정 기술과 표준 패턴을 사용해 개발된 웹 앱

```powershell
// 환경 설정
> npx.cmd create-next-app@latest
```

```
// 처리결과
Need to install the following packages:
  create-next-app@latest
Ok to proceed? (y)
√ What is your project named? ... app-scuba-eng
√ Would you like to use TypeScript with this project? ... No / Yes
√ Would you like to use ESLint with this project? ... No / Yes
Creating a new Next.js app in C:\Workspace\WebWork\app-scuba-eng.

Using npm.

Installing dependencies:
- react
- react-dom
- next
- eslint
- eslint-config-next


added 245 packages, and audited 246 packages in 20s

85 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

Initializing project with template: default

Initialized a git repository.

Success! Created app-scuba-eng at C:\Workspace\WebWork\app-scuba-eng

A new version of `create-next-app` is available!
You can update by running: npm i -g create-next-app
```

```
// 패키지 팩 설정 next.js pwa 기본 패키지 설정
> yarn add next-pwa
```

```
// Some code

yarn add v1.13.0
info No lockfile found.
[1/4] Resolving packages...
[2/4] Fetching packages...
info fsevents@2.3.2: The platform "win32" is incompatible with this module.
info "fsevents@2.3.2" is an optional dependency and failed compatibility check. Excluding it from installation.
[3/4] Linking dependencies...
warning "next-pwa > babel-loader@8.3.0" has unmet peer dependency "@babel/core@^7.0.0".
warning "next-pwa > babel-loader@8.3.0" has unmet peer dependency "webpack@>=2".
warning "next-pwa > clean-webpack-plugin@4.0.0" has unmet peer dependency "webpack@>=4.0.0 <6.0.0".
warning "next-pwa > terser-webpack-plugin@5.3.6" has unmet peer dependency "webpack@^5.1.0".
warning "next-pwa > workbox-webpack-plugin@6.5.4" has unmet peer dependency "webpack@^4.4.0 || ^5.9.0".
warning " > next-pwa@5.6.0" has unmet peer dependency "next@>=9.0.0".
[4/4] Building fresh packages...
success Saved lockfile.
success Saved 272 new dependencies.
info Direct dependencies
└─ next-pwa@5.6.0
info All dependencies
├─ @ampproject/remapping@2.2.0
├─ @babel/compat-data@7.20.1
├─ @babel/core@7.20.2
├─ @babel/generator@7.20.4
├─ @babel/helper-builder-binary-assignment-operator-visitor@7.18.9
├─ @babel/helper-compilation-targets@7.20.0
├─ @babel/helper-explode-assignable-expression@7.18.6
├─ @babel/helper-module-transforms@7.20.2
├─ @babel/helper-plugin-utils@7.20.2
├─ @babel/helper-remap-async-to-generator@7.18.9
├─ @babel/helper-simple-access@7.20.2
├─ @babel/helper-string-parser@7.19.4
├─ @babel/helper-validator-identifier@7.19.1
├─ @babel/helper-wrap-function@7.19.0
├─ @babel/helpers@7.20.1
├─ @babel/highlight@7.18.6
├─ @babel/parser@7.20.3
├─ @babel/plugin-bugfix-safari-id-destructuring-collision-in-function-expression@7.18.6
├─ @babel/plugin-bugfix-v8-spread-parameters-in-optional-chaining@7.18.9
├─ @babel/plugin-proposal-async-generator-functions@7.20.1
├─ @babel/plugin-proposal-class-properties@7.18.6
├─ @babel/plugin-proposal-class-static-block@7.18.6
├─ @babel/plugin-proposal-dynamic-import@7.18.6
├─ @babel/plugin-proposal-export-namespace-from@7.18.9
├─ @babel/plugin-proposal-json-strings@7.18.6
├─ @babel/plugin-proposal-logical-assignment-operators@7.18.9
├─ @babel/plugin-proposal-nullish-coalescing-operator@7.18.6
├─ @babel/plugin-proposal-numeric-separator@7.18.6
├─ @babel/plugin-proposal-object-rest-spread@7.20.2
├─ @babel/plugin-proposal-optional-catch-binding@7.18.6
├─ @babel/plugin-proposal-private-methods@7.18.6
├─ @babel/plugin-proposal-private-property-in-object@7.18.6
├─ @babel/plugin-proposal-unicode-property-regex@7.18.6
├─ @babel/plugin-syntax-class-properties@7.12.13
├─ @babel/plugin-syntax-import-assertions@7.20.0
├─ @babel/plugin-syntax-top-level-await@7.14.5
├─ @babel/plugin-transform-arrow-functions@7.18.6
├─ @babel/plugin-transform-async-to-generator@7.18.6
├─ @babel/plugin-transform-block-scoped-functions@7.18.6
├─ @babel/plugin-transform-block-scoping@7.20.2
├─ @babel/plugin-transform-classes@7.20.2
├─ @babel/plugin-transform-computed-properties@7.18.9
├─ @babel/plugin-transform-destructuring@7.20.2
├─ @babel/plugin-transform-dotall-regex@7.18.6
├─ @babel/plugin-transform-duplicate-keys@7.18.9
├─ @babel/plugin-transform-exponentiation-operator@7.18.6
├─ @babel/plugin-transform-for-of@7.18.8
├─ @babel/plugin-transform-function-name@7.18.9
├─ @babel/plugin-transform-literals@7.18.9
├─ @babel/plugin-transform-member-expression-literals@7.18.6
├─ @babel/plugin-transform-modules-amd@7.19.6
├─ @babel/plugin-transform-modules-commonjs@7.19.6
├─ @babel/plugin-transform-modules-systemjs@7.19.6
├─ @babel/plugin-transform-modules-umd@7.18.6
├─ @babel/plugin-transform-named-capturing-groups-regex@7.19.1
├─ @babel/plugin-transform-new-target@7.18.6
├─ @babel/plugin-transform-object-super@7.18.6
├─ @babel/plugin-transform-property-literals@7.18.6
├─ @babel/plugin-transform-regenerator@7.18.6
├─ @babel/plugin-transform-reserved-words@7.18.6
├─ @babel/plugin-transform-shorthand-properties@7.18.6
├─ @babel/plugin-transform-spread@7.19.0
├─ @babel/plugin-transform-sticky-regex@7.18.6
├─ @babel/plugin-transform-template-literals@7.18.9
├─ @babel/plugin-transform-typeof-symbol@7.18.9
├─ @babel/plugin-transform-unicode-escapes@7.18.10
├─ @babel/plugin-transform-unicode-regex@7.18.6
├─ @babel/preset-env@7.20.2
├─ @babel/preset-modules@0.1.5
├─ @babel/runtime@7.20.1
├─ @babel/traverse@7.20.1
├─ @jridgewell/gen-mapping@0.3.2
├─ @jridgewell/resolve-uri@3.1.0
├─ @jridgewell/set-array@1.1.2
├─ @jridgewell/source-map@0.3.2
├─ @nodelib/fs.scandir@2.1.5
├─ @nodelib/fs.stat@2.0.5
├─ @nodelib/fs.walk@1.2.8
├─ @rollup/plugin-babel@5.3.1
├─ @rollup/plugin-node-resolve@11.2.1
├─ @rollup/plugin-replace@2.4.2
├─ @surma/rollup-plugin-off-main-thread@2.2.3
├─ @types/estree@0.0.39
├─ @types/glob@7.2.0
├─ @types/json-schema@7.0.11
├─ @types/minimatch@5.1.2
├─ @types/resolve@1.17.1
├─ @types/trusted-types@2.0.2
├─ acorn@8.8.1
├─ ajv@6.12.6
├─ ansi-styles@3.2.1
├─ array-union@2.1.0
├─ array-uniq@1.0.3
├─ async@3.2.4
├─ at-least-node@1.0.0
├─ babel-loader@8.3.0
├─ babel-plugin-polyfill-corejs2@0.3.3
├─ babel-plugin-polyfill-corejs3@0.6.0
├─ babel-plugin-polyfill-regenerator@0.4.1
├─ big.js@5.2.2
├─ brace-expansion@1.1.11
├─ braces@3.0.2
├─ browserslist@4.21.4
├─ buffer-from@1.1.2
├─ builtin-modules@3.3.0
├─ caniuse-lite@1.0.30001431
├─ chalk@2.4.2
├─ clean-webpack-plugin@4.0.0
├─ color-convert@1.9.3
├─ color-name@1.1.3
├─ commander@2.20.3
├─ common-tags@1.8.2
├─ commondir@1.0.1
├─ concat-map@0.0.1
├─ convert-source-map@1.9.0
├─ crypto-random-string@2.0.0
├─ debug@4.3.4
├─ deepmerge@4.2.2
├─ del@4.1.1
├─ dir-glob@3.0.1
├─ ejs@3.1.8
├─ electron-to-chromium@1.4.284
├─ emojis-list@3.0.0
├─ es-abstract@1.20.4
├─ es-to-primitive@1.2.1
├─ escalade@3.1.1
├─ escape-string-regexp@1.0.5
├─ estree-walker@1.0.1
├─ esutils@2.0.3
├─ fast-glob@3.2.12
├─ fastq@1.13.0
├─ filelist@1.0.4
├─ fill-range@7.0.1
├─ find-cache-dir@3.3.2
├─ find-up@4.1.0
├─ fs-extra@9.1.0
├─ fs.realpath@1.0.0
├─ function.prototype.name@1.1.5
├─ gensync@1.0.0-beta.2
├─ get-own-enumerable-property-symbols@3.0.2
├─ get-symbol-description@1.0.0
├─ glob-parent@5.1.2
├─ glob@7.2.3
├─ globby@11.1.0
├─ graceful-fs@4.2.10
├─ has-bigints@1.0.2
├─ ignore@5.2.0
├─ inflight@1.0.6
├─ inherits@2.0.4
├─ is-bigint@1.0.4
├─ is-boolean-object@1.1.2
├─ is-callable@1.2.7
├─ is-core-module@2.11.0
├─ is-date-object@1.0.5
├─ is-extglob@2.1.1
├─ is-glob@4.0.3
├─ is-module@1.0.0
├─ is-negative-zero@2.0.2
├─ is-number-object@1.0.7
├─ is-number@7.0.0
├─ is-obj@1.0.1
├─ is-path-cwd@2.2.0
├─ is-path-in-cwd@2.1.0
├─ is-path-inside@2.1.0
├─ is-regexp@1.0.0
├─ is-shared-array-buffer@1.0.2
├─ is-stream@2.0.1
├─ is-string@1.0.7
├─ is-symbol@1.0.4
├─ is-weakref@1.0.2
├─ jake@10.8.5
├─ jest-worker@27.5.1
├─ js-tokens@4.0.0
├─ jsesc@2.5.2
├─ json-schema-traverse@0.4.1
├─ json-schema@0.4.0
├─ json5@2.2.1
├─ jsonfile@6.1.0
├─ jsonpointer@5.0.1
├─ leven@3.1.0
├─ loader-utils@2.0.4
├─ locate-path@5.0.0
├─ lodash.debounce@4.0.8
├─ lodash.sortby@4.7.0
├─ lodash@4.17.21
├─ magic-string@0.25.9
├─ make-dir@3.1.0
├─ merge2@1.4.1
├─ micromatch@4.0.5
├─ minimatch@3.1.2
├─ ms@2.1.2
├─ next-pwa@5.6.0
├─ node-releases@2.0.6
├─ object-assign@4.1.1
├─ object-inspect@1.12.2
├─ object.assign@4.1.4
├─ p-limit@2.3.0
├─ p-locate@4.1.0
├─ p-map@2.1.0
├─ p-try@2.2.0
├─ path-exists@4.0.0
├─ path-is-absolute@1.0.1
├─ path-is-inside@1.0.2
├─ path-parse@1.0.7
├─ path-type@4.0.0
├─ picocolors@1.0.0
├─ picomatch@2.3.1
├─ pify@4.0.1
├─ pinkie-promise@2.0.1
├─ pinkie@2.0.4
├─ pkg-dir@4.2.0
├─ pretty-bytes@5.6.0
├─ queue-microtask@1.2.3
├─ regenerate-unicode-properties@10.1.0
├─ regenerator-runtime@0.13.11
├─ regenerator-transform@0.15.1
├─ regexpu-core@5.2.2
├─ regjsgen@0.7.1
├─ regjsparser@0.9.1
├─ require-from-string@2.0.2
├─ resolve@1.22.1
├─ reusify@1.0.4
├─ rimraf@2.7.1
├─ rollup-plugin-terser@7.0.2
├─ rollup@2.79.1
├─ run-parallel@1.2.0
├─ safe-buffer@5.2.1
├─ safe-regex-test@1.0.0
├─ schema-utils@2.7.1
├─ semver@6.3.0
├─ serialize-javascript@6.0.0
├─ slash@3.0.0
├─ source-list-map@2.0.1
├─ source-map-support@0.5.21
├─ source-map@0.6.1
├─ sourcemap-codec@1.4.8
├─ string.prototype.matchall@4.0.8
├─ string.prototype.trimend@1.0.6
├─ string.prototype.trimstart@1.0.6
├─ stringify-object@3.3.0
├─ strip-comments@2.0.1
├─ supports-color@7.2.0
├─ supports-preserve-symlinks-flag@1.0.0
├─ temp-dir@2.0.0
├─ tempy@0.6.0
├─ terser-webpack-plugin@5.3.6
├─ terser@5.15.1
├─ to-fast-properties@2.0.0
├─ to-regex-range@5.0.1
├─ tr46@1.0.1
├─ type-fest@0.16.0
├─ unbox-primitive@1.0.2
├─ unicode-canonical-property-names-ecmascript@2.0.0
├─ unicode-match-property-ecmascript@2.0.0
├─ unicode-match-property-value-ecmascript@2.1.0
├─ unicode-property-aliases-ecmascript@2.1.0
├─ unique-string@2.0.0
├─ update-browserslist-db@1.0.10
├─ webidl-conversions@4.0.2
├─ webpack-sources@1.4.3
├─ whatwg-url@7.1.0
├─ which-boxed-primitive@1.0.2
├─ workbox-broadcast-update@6.5.4
├─ workbox-build@6.5.4
├─ workbox-google-analytics@6.5.4
├─ workbox-navigation-preload@6.5.4
├─ workbox-range-requests@6.5.4
├─ workbox-recipes@6.5.4
├─ workbox-streams@6.5.4
├─ workbox-sw@6.5.4
├─ workbox-webpack-plugin@6.5.4
└─ workbox-window@6.5.4
Done in 8.07s.
PS C:\Workspace\WebWork>
```

export 구성을 위한 패키지 추가

```powershell
// Some code
> yarn add --dev next-compose-plugins
```

```
yarn add v1.13.0
warning package.json: No license field
warning No license field
[1/4] Resolving packages...
[2/4] Fetching packages...
info fsevents@2.3.2: The platform "win32" is incompatible with this module.
info "fsevents@2.3.2" is an optional dependency and failed compatibility check. Excluding it from installation.
[3/4] Linking dependencies...
warning " > next-pwa@5.6.0" has unmet peer dependency "next@>=9.0.0".
warning "next-pwa > babel-loader@8.3.0" has unmet peer dependency "@babel/core@^7.0.0".
warning "next-pwa > babel-loader@8.3.0" has unmet peer dependency "webpack@>=2".
warning "next-pwa > clean-webpack-plugin@4.0.0" has unmet peer dependency "webpack@>=4.0.0 <6.0.0".
warning "next-pwa > terser-webpack-plugin@5.3.6" has unmet peer dependency "webpack@^5.1.0".
warning "next-pwa > workbox-webpack-plugin@6.5.4" has unmet peer dependency "webpack@^4.4.0 || ^5.9.0".
[4/4] Building fresh packages...

success Saved lockfile.
warning No license field
success Saved 1 new dependency.
info Direct dependencies
└─ next-compose-plugins@2.2.1
info All dependencies
└─ next-compose-plugins@2.2.1
Done in 1.69s.
```

export 설정을 위한 next.config.js 수정

```
/** @type {import('next').NextConfig} */
const withPlugins = require("next-compose-plugins");
const withPWA = require("next-pwa");

const nextConfig = {
  reactStrictMode: true,
}

module.exports = withPlugins(
	[
		[
			withPWA,
			{
				pwa: {
					dest: "public",
				},
			},
		],
	],
	nextConfig
);
```

매니페스트 작성

{% embed url="https://www.simicart.com/manifest-generator.html/" %}
웹사이트를 이용해서 매니페스트 작성
{% endembed %}

아이콘 작성

{% embed url="https://tools.crawlink.com/tools/pwa-icon-generator/" %}
웹사이트르ㄹ 이용해서 아이콘셋 구성
{% endembed %}

메타태그 적용

```javascript
import { Html, Head, Main, NextScript } from 'next/document'

export default function Document() {
  return (
    <Html lang="ko">
      <Head>
        <link rel="manifest" href="/manifest.json" />
        <link
            href="assets/icons/favicon-16x16.png"
            rel="icon"
            type="image/png"
            sizes="16x16"
        />
        <link
            href="assets/icons/favicon-32x32.png"
            rel="icon"
            type="image/png"
            sizes="32x32"
        />
        <link rel="apple-touch-icon" href="assets/icons/icon-192x192.png"></link>
        <meta name="msapplication-TileColor" content="#FF98BA"></meta>
        <link href="splashscreens/iphone5_splash.png" media="(device-width: 320px) and (device-height: 568px) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image" />
        <link href="splashscreens/iphone6_splash.png" media="(device-width: 375px) and (device-height: 667px) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image" />
        <link href="splashscreens/iphoneplus_splash.png" media="(device-width: 621px) and (device-height: 1104px) and (-webkit-device-pixel-ratio: 3)" rel="apple-touch-startup-image" />
        <link href="splashscreens/iphonex_splash.png" media="(device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3)" rel="apple-touch-startup-image" />
        <link href="splashscreens/iphonexr_splash.png" media="(device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image" />
        <link href="splashscreens/iphonexsmax_splash.png" media="(device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 3)" rel="apple-touch-startup-image" />
        <link href="splashscreens/ipad_splash.png" media="(device-width: 768px) and (device-height: 1024px) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image" />
        <link href="splashscreens/ipadpro1_splash.png" media="(device-width: 834px) and (device-height: 1112px) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image" />
        <link href="splashscreens/ipadpro3_splash.png" media="(device-width: 834px) and (device-height: 1194px) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image" />
        <link href="splashscreens/ipadpro2_splash.png" media="(device-width: 1024px) and (device-height: 1366px) and (-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image" />
        <meta name="apple-mobile-web-app-capable" content="yes"></meta>
      </Head>
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  )
}
```

pages폴더에\_document.js 파일 작성

{% embed url="https://appsco.pe/developer/splash-screens" %}
웹사이트를   이용한 아이폰 스플래쉬 페이지 작성
{% endembed %}



실행

```powershell
> yarn build && yarn dev
```

```
yarn run v1.13.0
warning ..\package.json: No license field
$ next build
warn  - Invalid next.config.js options detected: 
  - The root value has an unexpected property, webpackDevMiddleware, which is not in the list of allowed properties (amp, analyticsId, assetPrefix, basePath, cleanDistDir, compiler, compress, crossOrigin, devIndicators, distDir, env, eslint, excludeDefaultMomentLocales, experimental, exportPathMap, generateBuildId, generateEtags, headers, httpAgentOptions, i18n, images, onDemandEntries, optimizeFonts, output, outputFileTracing, pageExtensions, poweredByHeader, productionBrowserSourceMaps, publicRuntimeConfig, reactStrictMode, redirects, rewrites, sassOptions, serverRuntimeConfig, staticPageGenerationTimeout, swcMinify, trailingSlash, typescript, useFileSystemPublicRoutes, webpack).
  - The root value has an unexpected property, configOrigin, which is not in the list of allowed properties (amp, analyticsId, assetPrefix, basePath, cleanDistDir, compiler, compress, crossOrigin, devIndicators, distDir, env, eslint, excludeDefaultMomentLocales, experimental, exportPathMap, generateBuildId, generateEtags, headers, httpAgentOptions, i18n, images, onDemandEntries, optimizeFonts, output, outputFileTracing, pageExtensions, poweredByHeader, productionBrowserSourceMaps, publicRuntimeConfig, reactStrictMode, redirects, rewrites, sassOptions, serverRuntimeConfig, staticPageGenerationTimeout, swcMinify, trailingSlash, typescript, useFileSystemPublicRoutes, webpack).  
  - The root value has an unexpected property, target, which is not in the list of allowed properties (amp, analyticsId, assetPrefix, basePath, cleanDistDir, compiler, compress, crossOrigin, devIndicators, distDir, env, eslint, excludeDefaultMomentLocales, experimental, exportPathMap, generateBuildId, generateEtags, headers, httpAgentOptions, i18n, images, onDemandEntries, optimizeFonts, output, outputFileTracing, pageExtensions, poweredByHeader, productionBrowserSourceMaps, publicRuntimeConfig, reactStrictMode, redirects, rewrites, sassOptions, serverRuntimeConfig, staticPageGenerationTimeout, swcMinify, trailingSlash, typescript, useFileSystemPublicRoutes, webpack).        
  - The value at .amp.canonicalBase must be 1 character or more but it was 0 characters.
  - The value at .assetPrefix must be 1 character or more but it was 0 characters.
  - The value at .experimental.outputFileTracingRoot must be 1 character or more but it was 0 characters.
  - The value at .i18n must be an object but it was null.
  - The value at .images.loaderFile must be 1 character or more but it was 0 characters.
  - The value at .webpack must be a function that returns a webpack configuration object.

See more info here: https://nextjs.org/docs/messages/invalid-next-config
info  - Linting and checking validity of types
info  - Creating an optimized production build  
info  - Compiled successfully
info  - Collecting page data  
info  - Generating static pages (3/3)
info  - Finalizing page optimization

Route (pages)                              Size     First Load JS
┌ ○ /                                      4.32 kB        77.4 kB
├   └ css/ae0e3e027412e072.css             707 B
├   /_app                                  0 B            73.1 kB
├ ○ /404                                   181 B          73.3 kB
└ λ /api/hello                             0 B            73.1 kB
+ First Load JS shared by all              73.4 kB
  ├ chunks/framework-8c5acb0054140387.js   45.4 kB
  ├ chunks/main-b482fffd82fa7e1c.js        26.7 kB
  ├ chunks/pages/_app-2398585b21d2d8c8.js  285 B
  ├ chunks/webpack-8fa1640cc84ba8fe.js     750 B
  └ css/ab44ce7add5c3d11.css               247 B

λ  (Server)  server-side renders at runtime (uses getInitialProps or getServerSideProps)
○  (Static)  automatically rendered as static HTML (uses no initial props)

Done in 11.09s.
yarn run v1.13.0
warning ..\package.json: No license field
$ next dev
ready - started server on 0.0.0.0:3000, url: http://localhost:3000
warn  - Invalid next.config.js options detected: 
  - The root value has an unexpected property, webpackDevMiddleware, which is not in the list of allowed properties (amp, analyticsId, assetPrefix, basePath, cleanDistDir, compiler, compress, crossOrigin, devIndicators, distDir, env, eslint, excludeDefaultMomentLocales, experimental, exportPathMap, generateBuildId, generateEtags, headers, httpAgentOptions, i18n, images, onDemandEntries, optimizeFonts, output, outputFileTracing, pageExtensions, poweredByHeader, productionBrowserSourceMaps, publicRuntimeConfig, reactStrictMode, redirects, rewrites, sassOptions, serverRuntimeConfig, staticPageGenerationTimeout, swcMinify, trailingSlash, typescript, useFileSystemPublicRoutes, webpack).
  - The root value has an unexpected property, configOrigin, which is not in the list of allowed properties (amp, analyticsId, assetPrefix, basePath, cleanDistDir, compiler, compress, crossOrigin, devIndicators, distDir, env, eslint, excludeDefaultMomentLocales, experimental, exportPathMap, generateBuildId, generateEtags, headers, httpAgentOptions, i18n, images, onDemandEntries, optimizeFonts, output, outputFileTracing, pageExtensions, poweredByHeader, productionBrowserSourceMaps, publicRuntimeConfig, reactStrictMode, redirects, rewrites, sassOptions, serverRuntimeConfig, staticPageGenerationTimeout, swcMinify, trailingSlash, typescript, useFileSystemPublicRoutes, webpack).  
  - The root value has an unexpected property, target, which is not in the list of allowed properties (amp, analyticsId, assetPrefix, basePath, cleanDistDir, compiler, compress, crossOrigin, devIndicators, distDir, env, eslint, excludeDefaultMomentLocales, experimental, exportPathMap, generateBuildId, generateEtags, headers, httpAgentOptions, i18n, images, onDemandEntries, optimizeFonts, output, outputFileTracing, pageExtensions, poweredByHeader, productionBrowserSourceMaps, publicRuntimeConfig, reactStrictMode, redirects, rewrites, sassOptions, serverRuntimeConfig, staticPageGenerationTimeout, swcMinify, trailingSlash, typescript, useFileSystemPublicRoutes, webpack).        
  - The value at .amp.canonicalBase must be 1 character or more but it was 0 characters.
  - The value at .assetPrefix must be 1 character or more but it was 0 characters.
  - The value at .experimental.outputFileTracingRoot must be 1 character or more but it was 0 characters.
  - The value at .i18n must be an object but it was null.
  - The value at .images.loaderFile must be 1 character or more but it was 0 characters.
  - The value at .webpack must be a function that returns a webpack configuration object.

See more info here: https://nextjs.org/docs/messages/invalid-next-config
event - compiled client and server successfully in 412 ms (156 modules)
wait  - compiling /_error (client and server)...
event - compiled client and server successfully in 67 ms (157 modules)
warn  - Fast Refresh had to perform a full reload. Read more: https://nextjs.org/docs/basic-features/fast-refresh#how-it-works
TypeError: Cannot read properties of null (reading 'length')
    at eval (webpack-internal:///./node_modules/next/dist/client/dev/error-overlay/hot-dev-client.js:262:55)
wait  - compiling / (client and server)...
event - compiled client and server successfully in 74 ms (186 modules)

```

최종 next.config.js

```
/** @type {import('next').NextConfig} */
const withPlugins = require("next-compose-plugins");
const withPWA = require("next-pwa");
const webpack = require("webpack");
const optimizedImages = require('next-optimized-images')

const nextConfig = {
  reactStrictMode: true,
  eslint: {
    // ESLint managed on the workspace level
    ignoreDuringBuilds: true,
  },
  images: {
    loader: 'akamai',
    path: './',
  },
  assetPrefix: './', 
  webpack(config) {
    //console.log(config);

    // 플러그인 관련 설정
    const plugins = [
      ...config.plugins,
      new webpack.ContextReplacementPlugin(/moment[/\\]locale$/, /^\.\/ko$/),	
    ];
    return {
      ...config,
      mode: "production",
      devtool: "hidden-source-map",
      plugins: plugins,
    };
  },
};

module.exports = withPlugins(
	[
		[
			withPWA,
			{
				pwa: {
					dest: "public",
				},
			},
		],
	],
	nextConfig
);
```
