# Job Offers Application

## Home Page Route

home page contains 3 components

1. **SearchBox**
2. **Filter** works well except location and category which are by default set to all and the default sort option is *alphabetical*.
3. **Offers** which is composed of *offer* components

### Offer Component

contains the information about a particular offer which is passed as prop and it has a sub component called *Detail* which is used 4 times in one offer component.

## Application Route

application route renders the form to apply for a given form and then submit it using an API created using express and  stores it in mongodb.

The route also contains the id of offer which has no use for now, about it can be used to get the person who created that offer and then send him/her an email that someone has shown interest to his/her offer.

## CreateOffer Route

It renders the form to create new offer and then stores it to firebase and updates the home page offers also.
When the offerCreation form is submitted it sends a *put* request to firebase. And when the page loads for the first time it makes a *get* request to firebase but not any *put* request on the first time because it will overwrite the existing data.

But I have hard coded some offers in the *offers-slice.js* file as a fallback because sometimes the *put* request was being made even in the first render(overwriting the existing data) before the *get* request.


## Some features of this app

1. Anyone is able to create more offers in createOffer route.
2. All the pages are responsive.
3. Lazy Loading so that all the code is not loaded in one time, but only when it is needed.
4. Forms can't be submitted until all the fields are valid.
5. Apply for an offer from *apply now* link of an offer.
6. Filter the offers according to different parameters (except location and category)

To Start the app :

1. run `npm start` in the root of fronted folder.
2. And then run `npm run dev` in the root of backend folder.