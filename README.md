# Simple Restaurant Menu App

A simple menu app that is designed for small coffees and restaurants. VueJS is used the frontend framework.

<img width="300" alt="image" src="https://user-images.githubusercontent.com/24893654/155282165-05123803-d056-4c88-986c-ec52bda53235.png"> <img width="300" alt="image" src="https://user-images.githubusercontent.com/24893654/155282256-83c5d5fe-e9d2-43eb-8aa6-17c85310ae81.png"> <img width="300" alt="image" src="https://user-images.githubusercontent.com/24893654/155282284-7c0415a8-b39c-4691-840c-e016f640f891.png">

## How to Update the menu

All the data is consumed from `src/data/data.js`

Categories and products can be easily managed there.
 
```
 categories: [
        {
            name: 'Kırmızı etler',
            image: 'https://adisyostorage.blob.core.windows.net/mahrezphotos/category.png',
            items: [
                {
                    name: 'SAR-BURGER',
                    price: '30 tl',
                    image: require("../assets/sarburger.jpeg")
                },
            ]
         },
]         
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

## How to get docker build

```
docker build -t dockerhost.com/menu-app .
docker push dockerhost.com/menu-app
```
