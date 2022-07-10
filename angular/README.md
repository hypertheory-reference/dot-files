# Angular Stuff

In this folder there is a `.vscode` folder you can drop into an Angular project.

> The Angular CLI adds the `.vscode` folder to the gitignore. Remove that if you want this to travel with your repo.

## Snippets

### `NGRX-ROOT-REDUCER`

```typescript
import { ActionReducerMap } from "@ngrx/store";

export interface AppState {}

export const reducers: ActionReducerMap<AppState> = {};
```

### `NGRX-FEATURE-REDUCER`

```typescript
import { ActionReducerMap, createFeatureSelector } from "@ngrx/store";

export const featureName = "featureName";

export interface FeatureInterface {}

export const reducers: ActionReducerMap<FeatureInterface> = {};

const selectFeature = createFeatureSelector<FeatureInterface>(featureName);
```

### `NGRX-ENTITY-REDUCER`

creates an Entity Reducer

```typescript
import { EntityState, createEntityAdapter } from "@ngrx/entity";
import { createReducer, Action, on } from "@ngrx/store";

export interface EntityInterface {}

export interface State extends EntityState<EntityInterface> {}

export const adapter = createEntityAdapter<EntityInterface>();

const initialState = adapter.getInitialState();

export const reducer = createReducer(initialState);
```

### `NGRX-EFFECT`

This creates an Effect for use in an effects class.

> Note: I don't like this one, usually just type it.

```typescript

```

### Actions Pre-Angular 14

#### `NGRX-ACTION-FILE`

```typescript
import { createAction, props } from "@ngrx/store";

export const Events = {};

export const Commands = {};

export const Documents = {};
```

In that file you can use the following to create Actions:

- `NGRX-ACTION-EMPTY`
  - An Empty Action
- `NGRX-ACTION-PROPS`
  - An Action that takes Props

```typescript
import { createAction, props } from "@ngrx/store";

export const Events = {
  ActionName: createAction("[feature] action description"),
};

export const Commands = {};

export const Documents = {
  Document: createAction(
    "[feature] action description",
    props<{ payload: Message }>()
  ),
};
```

### NGRX ActionGroup Angular 14

> Coming soon.

### Jasmine Testing

Just two basic ones.

#### `desc`

```typescript
describe("what", () => {});
```

#### `it`

```typescript
it("what", () => {});
```
