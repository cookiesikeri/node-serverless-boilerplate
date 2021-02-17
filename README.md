## node-serverless-boilerplate

A starter kit for a serverless apaleo client gently offer by [limehome-engineering](https://medium.com/limehome-engineering) 🙌 ✌️.

### Serverless setup via NPM

Note: If you don’t already have Node on your machine, you’ll need to install it first. We suggest using the latest LTS version of NodeJS.

Install the [serverless](https://www.serverless.com/framework/docs/getting-started/) CLI:

1. `npm install serverless -g`

### Quickstart

1. Run `npm install`
2. Create an `.env` file based on `.env.example`
3. Run `npm run local`

### Deploy on AWS

1. Read about [serverless & AWS credentials](https://www.serverless.com/framework/docs/providers/aws/guide/credentials/)
2. Run `npm run serverless -- deploy --stage={stage to deploy for}` to deploy on AWS

### How to update apaleo api proxy?
Grab the latest version of a `swagger.json` for any service that needs to be updated. 
The link to `swagger.json` file can be found here:
- [apaleo Core API](https://api.apaleo.com/swagger)
- [apaleo Webhook API](https://webhook.apaleo.com/swagger)

Once you have the `swagger.json` locally, navigate to the `/src/generated/apaleo` folder and copy the file into the folder.
Then, pick the corresponding `autorest-{service}.yaml` and call autorest, for example:
```bash
autorest .\autorest-booking.yaml
```

Once the proxy is generated successfully - make sure you removed the `swagger.json` from the project.

### How to add a new apaleo api proxy?
Like the previous part, you will need to have a `swagger.json` file first and put it inside the folder in `/src/generated/apaleo`. From that moment, everything is pretty straightforward. 
Just go to the folder and create a new `autorest-{service}.yaml` file, based on any other configuration file there. And in this folder just run:
```bash
autorest .\autorest-{new_service}.yaml
```

### Contribution

Feel free to open an issue if you found any error or to create a pull request if want to add additional content.
