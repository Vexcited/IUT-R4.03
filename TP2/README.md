# Travail demandé

## A. Effectuer les recherches suivantes

### 1. Ventes faites par téléphone

```javascript
db.sales.find({ purchaseMethod: "Phone" })
```

### 2. Ventes faites en boutique et pour lesquelles un coupon a été utilisé.

```javascript
db.sales.find({ purchaseMethod: "In store", couponUsed: true })
```

### 3. Clients masculins de plus de 75 ans.

```javascript
db.sales.find({ customer: {
  age: {
    $gte: 75
    }
  }
}).count()
```

### 4. Ventes réalisées en ligne pour lesquelles la satisfaction est supérieure ou égale à 4, triées par satisfaction décroissante.

```javascript
db.sales.find({
  purchaseMethod: "Online",
  "customer.satisfaction": {
    $gte: 4
  }
}).sort({
  "customer.satisfaction": -1
})
```

### 5. Clients dont le genre n’est ni masculin ni féminin.

```javascript
db.sales.find({
  $nor: [
    { "customer.gender": "F" },
    { "customer.gender": "M" }
  ]
})
```

### 6. Liste des emplacements des boutiques.

```javascript
db.sales.distinct("storeLocation")
```

## B. Effectuer les recherches suivantes

### 1. Ventes contenant un laptop dont le prix est supérieur à 1500. On veut uniquement les items, la date de l’achat, et l’email de l’acheteur. Rq : dans la partie projection, en répétant le critère « `items: { $elemMatch }` » on restreint la liste des items retournés à ceux qui valident ce critère.


---

UPDATE: 28/02/2025 : Je n'ai pas enregistré les nouvelles requêtes malheureusement...
