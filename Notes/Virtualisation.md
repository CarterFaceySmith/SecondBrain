A computer architecture wherein multiple [[Virtual Machines]] are on the same hardware, in a layer abstracted away from that same [[Hardware]].

## Why though?

- Enhance resource sharing by many user in parallel
- Replace and upgrade hardware on the fly, via moving to a different device while active
- Add devices without reboots
- Reduces downtime
- Etc.

Note: VMM and [[Hypervisor]] are used interchangeably.

## Kinds

### Bare-Metal Virtualisation (Type 1)

Hardware and VMM (Virtual Machine Manager) located on 'Ring 0' (highest privileges), with guest OSs and applications located on 'Ring 1' and 'Ring 3', what the fuck are rings? Just another term for system privilege levels.

#### Types of type 1
1. Monolithic: single kernel containing basically all functionality of the OS, single binary program
2. Microkernel: provides only critical services, e.g process scheduling and interrupt handling

### Hosted Virtualisation (Type 2)

Hypervisor loaded on top of OS, the guest OS runs on the hosted Hypervisor.

E.g. Parallels or VirtualBox

Generally an organisation will prefer type 1 as type 2 is more inefficient but general users will often use type 2 due to ease of use and setup, minimal expertise required.

### Full Virtualisation (Type 3)

The guest OS is unmodified and works in Ring 1, VMM works in Ring 0.

Privileged instructions used to be trapped via software interrupt, the VMM intercepted these traps and emulates the instruction on the fly. Now, we have a binary translator which overrides privileged instructions and places them in a translation cache for execution.

### Para Virtualisation

Guest OS modified at source code level so trapping and binary rewriting is no longer necessary, runtime changes can be avoided.

[[Hypervisor]] provides interfaces to accommodate critical kernel operations.

## [[Containers]]

## Trap-and-emulate

When the [[Operating Systems]] want to run a kernel only instruction in a VM, it traps to the hypervisor which then emulates that instruction.

See also:
- [[Hardware]]
- [[VMWare vMotion]]









