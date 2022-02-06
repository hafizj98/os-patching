# This role is to patch servers

**Setting inventory**
```yaml
    reboot_servers: "no" # by default "no", "yes" it will reboot the servers after patching
```
**Ansible tag**
```
pre_patch
run_patch
post_patch
```

**To Execute**
- Gitlab CI did not support interactive input, you can add if you are not running using Gitlab
```yaml
- name: Request confirmation
  pause:
    prompt: |

      The packages listed above will be upgraded. Do you want to continue ? 
      -> Press RETURN to continue.
      -> Press Ctrl+c and then "a" to abort.
  tags: pre_patch      
```
