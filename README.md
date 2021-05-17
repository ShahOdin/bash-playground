# bash-playground

# Setup

We have two child scripts:

- child1.sh (succeeds)
- child2.sh (fails)


We want to call them from parent scripts:

- parent12.sh

  which does the following:
  
  ```bash
  source child1.sh &&
  source child2.sh

  returnCode=$?
  echo "returnCode is: ${returnCode}"
  ```

- parent21.sh
  doing:
    
  ```bash
  source child2.sh &&
  source child1.sh

  returnCode=$?
  echo "returnCode is: ${returnCode}"
  ```


# Result

- `sh parent12.sh`

  ```
  Im Child1 and I succeed
  im child2 and I fail
  returnCode is: 5
  ```

- `sh parent21.sh`

  ```
  im Child2 and I fail
  returnCode is: 5
  ```
