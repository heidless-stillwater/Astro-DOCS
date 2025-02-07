


# QUICK REF
```
npm create astro@latest
--
mad-man-astro
--

npx astro sync    # setup types for typescript. Sets up a '.astro/types.d.ts' file  

```

# xata
- ## [Adding Serverless Databases to Astro with Xata!](https://www.youtube.com/watch?v=BMHTGri2u7k)
  - ## [GIT - EXEMPLAR - xata]()
```
npm create astro@latest -- --template with-tailwindcss xata-astro-3

npm install @xata.io/cli -g 

# initial login after install
xata auth login --force
--
generate API
subsequent logins is new API key

--

xata init

vi xata.ts
--

export const getXataClient = () => {
  if (instance) return instance;

  instance = new XataClient(
    { 
      apiKey: import.meta.env.XATA_API_KEY,
      branch: import.meta.env.XATA_BRANCH 
    }
  );
  return instance;
};

--

```

# [CSV File Examples](https://support.staffbase.com/hc/en-us/articles/360007108391-CSV-File-Examples)
```



```


# [DotEnv](https://www.freecodecamp.org/news/how-to-use-node-environment-variables-with-a-dotenv-file-for-node-js-and-npm/)
```
npm create astro@latest -- --template with-tailwindcss xata-astro-3

npm i dotenv

--
require('dotenv').config()

# remove 'module' entry from package.json


console.log(`XATA_API_KEY: ${process.env.XATA_API_KEY}`)


--

```



- ## [Get started with Astro and Xata](https://xata.io/docs/getting-started/astro)
```
npm create astro@latest -- --template with-tailwindcss xata-astro-



xata init   # init DB

mkdir DB-config
cd !$

curl --create-dirs -o seed/blog-posts.csv https://raw.githubusercontent.com/xataio/examples/main/seed/blog-posts.csv

xata import csv seed/blog-posts.csv --table Posts --create

xata pull main    # re-generate src/xata.ts to incorporate new DB info



```

# tailwind
- ## [Install Tailwind CSS with Astro](https://tailwindcss.com/docs/installation/framework-guides/astro)
```
# create with tailwind
npm create astro@latest -- --template with-tailwindcss xata-astro-1

# or 
npm create astro@latest test-1
cd test-1

# follow instructions in video

npm i -D @tailwindcss/typography

npx astro add image

```



# TypeScript
```

#npm install -g typescript   # install typescript globally

tsc   # typescript compiler

# new project
npm init -y                         # new node project
npm install typescript --save-dev   # install typescript
npx tsc --init                      # create typescript config file

npx astro sync  # setup types

# compile code
tsc   # run in dir. compiles all 'typescript' code into javascript


vi tsconfig.json
--
{
  "extends": "astro/tsconfigs/base",
  "include": [".astro/types.d.ts", "**/*"],
  "exclude": ["dist"],
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./*"],
      "@components/*": ["src/components/*"],
      "@layouts/*": ["src/layouts/*"],
      "@assets/*": ["src/assets/*"],
      "@types": ["src/types"],
      "@utils": ["src/utils"]
    }
  }
}
--

```

# [RESOURCE: The Inter typeface family](https://rsms.me/inter/)
```
download
copy to ./public/fonts
--
Inter-Regular.woff2
Inter-Italic.woff2
Inter-Bold.woff2
--

vi tailwind.config.js
--
/** @type {import('tailwindcss').Config} */
export default {
  content: ['./src/**/*.{astro,html,js,jsx,md,mdx,svelte,ts,tsx,vue}'],
  theme: {
    extend: {
      fontFamily: {
        sans: ['Inter', 'Helvetica', 'Arial', 'sans-serif']
      },
      fontSize: {
      }
    },
  },
  plugins: [
    require('@tailwindcss/typography')
  ],
}

--

vi ./layouts/Base.astro
--
<style>
	@font-face {
		font-family: 'Inter';
		font-style: normal;
		font-weight: 400;
		font-display: swap;
		src: url('/fonts/Inter-Regular.woff2') format('woff2');
	}

	@font-face {
		font-family: 'Inter';
		font-style: italic;
		font-weight: 400;
		font-display: swap;
		src: url('/fonts/Inter-Italic.woff2') format('woff2');
	}

	@font-face {
		font-family: 'Inter';
		font-style: bold;
		font-weight: 400;
		font-display: swap;
		src: url('/fonts/Inter-Bold.woff2') format('woff2');
	}

</style>
--


```

