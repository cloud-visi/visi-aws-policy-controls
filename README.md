# Cloud-Visi public policy test fixture

Public upstream: cloud-visi/visi-aws-policy-controls.
Public fork: cloudkeel/visi-aws-policy-controls.

Only the source in this directory would be published, with fresh Git history. No existing private repository, history, credential, state, plan file, account ID or backend configuration is copied.

Native gate: output-only Terraform plan, followed by a separate environment-gated job that performs no Terraform apply. Configure a new fixture-approval environment with cloudkeel as required reviewer and prevent self-review. Observe pending deployment; cancel before the gated job runs. No request to another reviewer is required.

Fork: pull_request workflow runs static Terraform init/validate only, contents read, no id-token permission, no secrets, no pull_request_target, no self-hosted runners, persist-credentials false.

Existing private fixtures, organization forking policy and AWS trust/permissions remain unchanged. This proves public-repository gate/fork behavior; private plan/policy-specific cases remain conditional. Connect this new public fixture only to isolated 8083 when approved.

Publication of only these provider-free files was explicitly approved by the owner on 17 October 2026.
