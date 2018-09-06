
## Example `webpack.config.js` with `babel-loader`

from http://kursjs.pl/kurs/es6/webpack.php
```js
module.exports = {
    entry: './src/js/app.js',
    output: {
        path: `${__dirname}/dist/js`,
        filename: 'bundle.js'
    },
    watch: true,
    mode: "development", //this option will be ignored if we use npm run build
    devtool: "source-map",
    module: {
        rules: [
            {
                test: /\.js$/,
                exclude: /node_modules/,
                use: {
                    loader: 'babel-loader',
                    options: {
                        presets: [["env", {
                            targets: {
                                browsers: ['> 1%', 'last 2 versions']
                            }
                        }]]
                    }
                }
            }
        ]
    }
}
```