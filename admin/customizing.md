# Customizing the Admin

## General
### Icon
### Show the Names of your Entities Instead of their IRIs

## List
### Add a field
```
import React, {Component} from 'react';
import {HydraAdmin, ListGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextField} from 'react-admin';

const BookListGuesser = props => (
  <ListGuesser {...props}>
    <TextField source={'newField'} label={'newField'} />
  </ListGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} list={BookListGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Customize a field

```
import React, {Component} from 'react';
import {HydraAdmin, ListGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextField} from 'react-admin';

const BookListGuesser = props => (
  <ListGuesser {...props}>
    <TextField source={'description'} label={'description'} style={{background: 'red'}} />
  </ListGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} list={BookListGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Remove or reorder field(s)

```
import React, {Component} from 'react';
import {HydraAdmin, ListGuesser, ResourceGuesser} from '@api-platform/admin';

const BookListGuesser = props => (
  <ListGuesser {...props} fields={['isbn', 'description']} />
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} list={BookListGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

## Show

### Add a field
```
import React, {Component} from 'react';
import {HydraAdmin, ShowGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextField} from 'react-admin';

const BookShowGuesser = props => (
  <ShowGuesser {...props}>
    <TextField source={'newField'} label={'newField'} />
  </ShowGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} show={BookShowGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Customize a field

```
import React, {Component} from 'react';
import {HydraAdmin, ShowGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextField} from 'react-admin';

const BookShowGuesser = props => (
  <ShowGuesser {...props}>
    <TextField source={'description'} label={'description'} style={{background: 'red'}} />
  </ShowGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} show={BookShowGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Remove or reorder field(s)

```
import React, {Component} from 'react';
import {HydraAdmin, ShowGuesser, ResourceGuesser} from '@api-platform/admin';

const BookShowGuesser = props => (
  <ShowGuesser {...props} fields={['isbn', 'description']} />
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} show={BookShowGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

## Create

### Add an input

```
import React, {Component} from 'react';
import {HydraAdmin, CreateGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextInput} from 'react-admin';

const BookCreateGuesser = props => (
  <CreateGuesser {...props}>
    <TextInput source={'newInput'} label={'newInput'} />
  </CreateGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} create={BookCreateGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Customize an input
```
import React, {Component} from 'react';
import {HydraAdmin, CreateGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextInput} from 'react-admin';

const BookCreateGuesser = props => (
  <CreateGuesser {...props}>
    <TextInput source={'description'} label={'description'} style={{background: 'red'}} />
  </CreateGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} create={BookCreateGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Remove or reorder input(s)

```
import React, {Component} from 'react';
import {HydraAdmin, CreateGuesser, ResourceGuesser} from '@api-platform/admin';

const BookCreateGuesser = props => (
  <CreateGuesser {...props} inputs={['description', 'isbn']} />
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} create={BookCreateGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

## Edit
### Add an input

```
import React, {Component} from 'react';
import {HydraAdmin, EditGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextInput} from 'react-admin';

const BookEditGuesser = props => (
  <EditGuesser {...props}>
    <TextInput source={'newInput'} label={'newInput'} />
  </EditGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} edit={BookEditGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Customize an input
```
import React, {Component} from 'react';
import {HydraAdmin, EditGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextInput} from 'react-admin';

const BookEditGuesser = props => (
  <EditGuesser {...props}>
    <TextInput source={'description'} label={'description'} style={{background: 'red'}} />
  </EditGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} edit={BookEditGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Remove or reorder input(s)

```
import React, {Component} from 'react';
import {HydraAdmin, EditGuesser, ResourceGuesser} from '@api-platform/admin';

const BookEditGuesser = props => (
  <EditGuesser {...props} inputs={['isbn', 'description']} />
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} edit={BookEditGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

### Custom validation

```
import React, {Component} from 'react';
import {HydraAdmin, EditGuesser, ResourceGuesser} from '@api-platform/admin';
import {TextInput} from 'react-admin';

const required = (message = 'Required') => value => value ? undefined : message;
const minLength = (max, message = 'Too short') => value => value && value.length < max ? message : undefined;

const validateTitle = [required(), minLength(50)];

const BookEditGuesser = props => (
  <EditGuesser {...props}>
    <TextInput source={'title'} label={'title'} validate={validateTitle} />
  </EditGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} edit={BookEditGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://demo.api-platform.com">
        <BookResourceGuesser name={'books'} />
      </HydraAdmin>
    );
  }
}

export default App;
```

## Customize a relation
### To an other entity

```
import React, {Component} from 'react';
import {HydraAdmin, ListGuesser, ResourceGuesser, ShowGuesser, CreateGuesser, EditGuesser} from '@api-platform/admin';
import {ReferenceField, TextField, ReferenceInput, SelectInput} from 'react-admin';

const BookReviewsField = (props) => (
  <ReferenceField reference={'authors'} {...props}>
    <TextField source="name"/>
  </ReferenceField>
);

const BookReviewsInput = (props) => (
  <ReferenceInput reference={'authors'} {...props}>
      <SelectInput optionText="name"/>
  </ReferenceInput>
);

const BookListGuesser = props => (
  <ListGuesser {...props}>
    <BookReviewsField source={'author'} />
  </ListGuesser>
);

const BookShowGuesser = props => (
  <ShowGuesser {...props}>
    <BookReviewsField source={'author'} />
  </ShowGuesser>
);

const BookCreateGuesser = props => (
  <CreateGuesser {...props}>
    <BookReviewsInput source={'author'} />
  </CreateGuesser>
);

const BookEditGuesser = props => (
  <EditGuesser {...props}>
    <BookReviewsInput source={'author'} />
  </EditGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} list={BookListGuesser} show={BookShowGuesser} create={BookCreateGuesser} edit={BookEditGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://localhost:8443">
        <BookResourceGuesser name={'books'}/>
      </HydraAdmin>
    );
  }
}

export default App;
```

### To a collection

```
import React, {Component} from 'react';
import {HydraAdmin, ListGuesser, ResourceGuesser, ShowGuesser, CreateGuesser, EditGuesser} from '@api-platform/admin';
import {ReferenceArrayField, SingleFieldList, ChipField, ReferenceArrayInput, SelectArrayInput} from 'react-admin';

const BookReviewsField = (props) => (
  <ReferenceArrayField reference={'reviews'} {...props}>
    <SingleFieldList>
      <ChipField source="body"/>
    </SingleFieldList>
  </ReferenceArrayField>
);

const BookReviewsInput = (props) => (
  <ReferenceArrayInput reference={'reviews'} {...props}>
      <SelectArrayInput optionText="id"/>
  </ReferenceArrayInput>
);

const BookListGuesser = props => (
  <ListGuesser {...props}>
    <BookReviewsField source={'reviews'} />
  </ListGuesser>
);

const BookShowGuesser = props => (
  <ShowGuesser {...props}>
    <BookReviewsField source={'reviews'} />
  </ShowGuesser>
);

const BookCreateGuesser = props => (
  <CreateGuesser {...props}>
    <BookReviewsInput source={'reviews'} />
  </CreateGuesser>
);

const BookEditGuesser = props => (
  <EditGuesser {...props}>
    <BookReviewsInput source={'reviews'} />
  </EditGuesser>
);

const BookResourceGuesser = props => (
  <ResourceGuesser {...props} list={BookListGuesser} show={BookShowGuesser} create={BookCreateGuesser} edit={BookEditGuesser} />
);

class App extends Component {
  render() {
    return (
      <HydraAdmin entrypoint="https://localhost:8443">
        <BookResourceGuesser name={'books'}/>
      </HydraAdmin>
    );
  }
}

export default App;
```

### Using an Autocomplete Input

## Advanced
### Managing Files and Images
