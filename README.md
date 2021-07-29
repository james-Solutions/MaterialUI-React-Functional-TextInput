This is a demo of how to handle Text input using the Material UI in a React functional component.</br>
You can find the demonstration at ```/src/demo.js```

```
import React, { useState } from "react";
import PropTypes from "prop-types";
import { withStyles } from "@material-ui/core/styles";
import Input from "@material-ui/core/Input";
import InputLabel from "@material-ui/core/InputLabel";
import FormHelperText from "@material-ui/core/FormHelperText";
import FormControl from "@material-ui/core/FormControl";

const styles = (theme) => ({
  container: {
    display: "flex",
    flexWrap: "wrap"
  },
  formControl: {
    margin: theme.spacing.unit
  }
});

const ComposedTextField = (props) => {
  const [input, setInput] = useState("Test");

  const handleInput = (event) => {
    setInput(event.target.value);
  };

  return (
    <div className={props.classes.container}>
      <FormControl className={props.classes.formControl}>
        <InputLabel htmlFor="name-simple">Name</InputLabel>
        <Input id="name-simple" value={input} onChange={handleInput} />
      </FormControl>
      <FormControl
        className={props.classes.formControl}
        aria-describedby="name-helper-text"
      >
        <InputLabel htmlFor="name-helper">Name</InputLabel>
        <Input id="name-helper" value={input} onChange={handleInput} />
        <FormHelperText id="name-helper-text">
          Some important helper text
        </FormHelperText>
      </FormControl>
      <FormControl className={props.classes.formControl} disabled>
        <InputLabel htmlFor="name-disabled">Name</InputLabel>
        <Input id="name-disabled" value={input} onChange={handleInput} />
        <FormHelperText>Disabled</FormHelperText>
      </FormControl>
      <FormControl
        className={props.classes.formControl}
        error
        aria-describedby="name-error-text"
      >
        <InputLabel htmlFor="name-error">Name</InputLabel>
        <Input id="name-error" value={input} onChange={handleInput} />
        <FormHelperText id="name-error-text">Error</FormHelperText>
      </FormControl>
    </div>
  );
};

ComposedTextField.propTypes = {
  classes: PropTypes.object.isRequired
};

export default withStyles(styles)(ComposedTextField);

```
