# Sagstudio
 
 
 N O T E :=> We are using .toPromise() in angular *, RXJS ^6 as Of Now .
 When we upgrade Studio, we need to follow these instructions as follows .  
 ----------------------------------------------------------------------------
 Usage of the "new" lastValueFrom:

From a functional perspective lastValueFrom is the function we should go for as  replacement of toPromise.
 And Use Try Catch Also to handle errors.
<>
import { lastValueFrom } from 'rxjs';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent {
  categories: any[];

  constructor(private inventoryService: InventoryService) {}

  public async loadCategories() {
    const categories$ = this.inventoryService.getCategories();
    this.categories = await lastValueFrom(categories$);
  }
}
 
## Development server

Run `npm run start` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.


 
## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
