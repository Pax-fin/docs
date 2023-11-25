# Explain: the Terraform Cloud sdlc

## Context

Unlike a normal code changeset where we merge a pull request and call it a day, our Terraform sdlc has a couple more
manual steps to ensure we don't delete real resources.

## GitHub Integration

1. When you create a pull request to a TFC (Terraform Cloud) aware repo, you'll see a link to
   a [speculative run](#speculative-runs).
2. When you merge a pull request, TFC will run another apply run that does a plan and awaits for you to review and
   hit `apply`.

TFC runs are linked to the pull request. Otherwise, you can navigate
to [Paxfinancial TFC](https://app.terraform.io/app/paxfinancial/workspaces) directly.

## Speculative runs

Terraform is all about declaring what you desire in the world, Terraform doing a reconciliation from its known state and
the actual world, and then taking actions to rectify the possible differences.

Speculative runs allow you to see **before any changes actually happen** what Terraform intends to do your environment.
This is basically your way to review the code changes for correctness. If you see something tagged for deletion that you
don't expect... then don't merge!

Underneath the hood, speculative runs are basically TFC running `terraform plan`.

## Apply runs

Always off of the trunk of your repo, the apply run is TFE running `terraform apply`.