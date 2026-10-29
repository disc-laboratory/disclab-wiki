# disc1 GPU Workstation User Guide

disc1 is the DISC lab's shared GPU workstation, with one NVIDIA RTX PRO 5000 (48 GB). Everyone has their own account and can only see their own files.

## Help

| Who | For |
| --- | --- |
| Bryan | Access approval, GPU bookings |
| Workstation admin (currently Zhicong SUN) | Technical issues |

## Get an account

1. Email Bryan with the subject “Request for a DISC1 GPU account”, cc the workstation admin, and include your preferred username: lowercase, no spaces, for example bryan.
2. Once approved, Bryan or the admin replies with a one-time password.
3. On the campus network, run `ssh <username>@10.87.53.78` and enter that password.
4. When asked for the **current password**, enter the one-time password **again**, then type your new password twice.
5. The session closes. Log in again with your new password.

If you cannot connect, disc1's address may have changed. Contact the workstation admin.

## Book the GPU

1. Check GPU usage and free slots in the **DISCLab GPU** calendar in Outlook. Make sure the total GPU demand at any one time stays below the 48 GB capacity.
2. Fill in the [DISC Lab GPU Reservation Request](https://forms.cloud.microsoft/Pages/ResponsePage.aspx?id=SJPOFSq-K0aPwOF2WpsgSqj62Z--naFKrt7dTNwfhZlUMkZLVVowNlFYOUw2RTZNMlg2VVBXWjBETy4u) form, stating your expected GPU memory (VRAM) use.
3. Wait for the approval email. Approved bookings appear in the calendar automatically.

Run GPU jobs only in your approved slot, and do not hold the machine for long periods without need. GPU work without a booking may be stopped.

## Run GPU work

Running programs on this GPU with your own account works just like on your own computer. We still strongly recommend Docker to isolate your code, so your projects do not interfere with each other, though it is not required. Docker is already set up for everyone:

Use the `docker` command as usual, without sudo. Add `--device nvidia.com/gpu=all` to use the GPU (not `--gpus all`). Test it once:

```bash
docker run --rm --device nvidia.com/gpu=all nvidia/cuda:12.8.1-base-ubuntu24.04 nvidia-smi
```

- Use images with **CUDA 12.8 or newer** (PyTorch 2.7 or newer). Older images do not run on this GPU.
- Mount your code with `-v ~/proj:/workspace` and shared datasets read-only with `-v /data/datasets:/datasets:ro`.
- Run `nvidia-smi` before starting, to see current GPU memory use.

For security, and so that one account's environment cannot affect another's, member accounts have no sudo, so `sudo apt install` will not work. Install what you need inside a Docker container or in your home folder (pip, conda, etc.). For system-level changes, contact the workstation admin, though we still suggest looking for an alternative first.

## Storage and limits

| Item | Limit |
| --- | --- |
| Each user's own home folder | Up to 400 GB. When it is full, writes fail. Check with `xfs_quota -c 'quota -h' /home` |
| Shared datasets | We recommend keeping your data in your own home folder. A shared dataset folder, `/data/datasets`, is also available read-only to save disk space. Ask Bryan or the admin to add a dataset |
| Memory and CPU | Up to 100 GB RAM and 24 CPU cores per person. Jobs above 100 GB are killed |
| Backup | **None.** Keep code in git and copies of important results elsewhere |

Container images count toward your quota; clean up with `docker system prune -a`.

## Rules

- Do not share accounts.
- Research work only; no mining or long-running services.
- Book before using the GPU.
- Accounts are locked when you leave the lab and deleted 30 days later.
