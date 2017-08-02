# Codedeploy

## Requirements

1. Needs to be added as a submodule

```
[submodule "codedeploy/common"]
	path = codedeploy/common
	url = git@github.com:skyscrapers/aws-codedeploy-scripts.git
	branch = master
```

2. Change appspec.yml to call it from the codedeploy/common directory
```
ApplicationStart:
  - location: common/register_with_elb.sh
    timeout: 300
ApplicationStop:
  - location: common/deregister_from_elb.sh
```
