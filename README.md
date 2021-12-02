# Automating-Infrastructure-on-Google-Cloud-with-Terraform-Challenge-Lab
https://www.cloudskillsboost.google/focuses/16502?parent=catalog
 source_tags = ["mynetwork"] fixes the error 
 
 Heres the fix.....
 resource "google_compute_firewall" "mynetwork-allow-http-ssh-rdp-icmp" { name = "mynetwork-allow-http-ssh-rdp-icmp" network = google_compute_network.mynetwork.self_link allow { protocol = "tcp" ports = ["22", "80", "3389"] } allow { protocol = "icmp" } source_tags = ["mynetwork"] }
