

# demo

```golang
package main

import (
	"github.com/recall704/ipset"
	"github.com/recall704/utils/exec"
	"github.com/sirupsen/logrus"
)

func main() {
	st := ipset.IPSet{
		Name:       "foobar",
		SetType:    ipset.HashIPPort,
		HashFamily: ipset.ProtocolFamilyIPV4,
	}
	iexec := exec.New()
	runner := ipset.New(iexec)

	err := runner.CreateSet(&st, false)
	if err != nil {
		logrus.Errorf("expected success, got %v", err)
	}
}
```