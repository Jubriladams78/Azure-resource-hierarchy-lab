# Design Decisions

## Why three Resource Groups instead of one?
Blast radius isolation — a misconfigured compute resource cannot affect
networking or governance. Mirrors CAF recommended patterns.

## Why assign RBAC at Management Group scope vs. Subscription?
MG-scope assignments inherit down. In a multi-subscription enterprise
this avoids duplicating role assignments per subscription.

## Why Contributor for the SP and not Owner?
Least privilege — Terraform only needs to manage resources, not assign
RBAC or manage billing. Owner would be over-privileged for IaC.

## Why remote state in Azure Blob vs. local state?
State locking prevents concurrent runs from corrupting state. Azure Blob
provides this natively. Local state is only appropriate for solo dev work.

## Why Audit effect on the tag policy, not Deny?
Start with Audit to establish a baseline of non-compliant resources
before enforcing Deny, which could block legitimate operations.
