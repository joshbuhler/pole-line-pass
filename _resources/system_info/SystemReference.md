# Wasatch 100 System Commands

> **Note:** All runner numbers should be three digits. For example, runner 94 would be input as `094`.

| Function 		| Syntax 		| Details |
|:--|:--|:--|
| Delete 		| `DELETE ###` 	| Deletes all runner times at current checkpoint only. |
| DNF - List	| `/D` 			| Lists runners that did not finish. |
| DNF - Runners | `/DR` 		| Lists runners that did not finish, ordered by runner number. |
| DNF - Time 	| `/DT`			| Lists runners that did not finish, ordered by time. |
| Runner Stats	| `/L###%`		| Returns times for runner `###` at checkpoint `%`. |
| Race Leaders	| `LEADS`		| Returns top 10 male, and top 5 female runners. |
| List Runners 	| `NUMBERLIST`	| Returns all runners, ordered by runner number. |
| Find Runner 	| `/N,<name>`	| Returns runners with surname `<name>` |
| Find Runner 	| `/N,<name>*`	| Returns runners with surname beginning with `<name>` |
| Runner Times 	| `/R###A` 		| Returns runner number, name, race position, estimated arrival at next checkpoint, and previous checkpoint times. |
| Runner Info	| `/R###`		| Returns current info for runner `###`. |
| Runner(s) Info| `/R###-###-###`| Returns current info for runners `###`, `###`, `###`, etc. Separate runners with dashes (`-`). |
| Runner Data Entry (Full) | `###,IIII,OOOO` | Enters the In (`I`) time and Out (`O`) time for runner ###. Times are in 24-hour format. |
| Runner Data Entry (In only) | `###,IIII,,` | Enters the In (`I`) time for runner ###. Times are in 24-hour format. |
| Runner Data Entry (Out only) | `###,,OOOO` | Enters the Out (`O`) time for runner ###. Times are in 24-hour format. |
| Audit | `/A,%` | Lists checkpoint % problem records, defaults to current checkpoint when `,%` omitted. |
| Checkpoint In- time list | `/C,%,T,[D]` | Lists all runner in-times at checkpoint % beginning at time T for the next D hours, ordered by runner number; D default is 2 when omitted. |
| Checkpoint Out- time list | `/CO,%,T,[D]` | Lists all runner out-times at checkpoint % beginning at time T for the next D hours, ordered by runner number; D default is 2 when omitted. |
| Checkpoint | `CHKPT` | Returns list of checkpoint names and letter designators |
| Checkpoint | `CHKPT=%` | Log on as checkpoint `%` |
| Delete | `DELETE ###` | Deletes all runner times at current checkpoint only |
| Enter a DNF | `DNF,###,T,C,W,H` | Classify a runner as Did Not Finish. To cancel or correct after accepted, call Net Control. |
| Final Check | `/F,% /F` | Lists all outstanding runners and checks for missing times; Defaults to current checkpoint when `,%` omitted. |
| Holding | `/H,% /H` | Lists runners currently at checkpoint `%` |
| Holding | `/H` | Lists runners currently at current checkpoint. |
| Incoming | `/I,%` | Lists next ten runners inbound to checkpoint `%` |
| Incoming | `/I,%,N` | Lists next “N” runners inbound to checkpoint `%` |
| Incoming | `/I` | Lists next ten runners inbound to current checkpoint. |
| Pending Arrivals | `/P,%` | Lists no. of runners not reported into checkpoint `%` and not DNF. |
| Pending Arrivals | `/P[D],%` | Total number outstanding and adds individual runner numbers. |
| Pending Arrivals | `/P` | Lists no. of runners not reported into current checkpoint and not DNF. |
| Temperature | `TEMP` | Lists temperatures reported at checkpoints. |
| Temperature | `TEMP=XX` | Enters temperature at current checkpoint. |

