# Setting Up Wazuh for Home Network Security

In my quest to bolster the security of my home network, I embarked on a journey to configure and deploy Wazuh, a robust Security Information and Event Management (SIEM) system. My aim was to create a security infrastructure that would actively monitor and respond to potential threats across my digital landscape.

## Getting Started

### Obtaining the Wazuh Virtual Appliance

I started by obtaining the Wazuh Virtual Appliance (OVA) from the [official website](https://wazuh.com/). This OVA would serve as the foundation for my home network's security operations.

### VirtualBox Deployment

With the OVA in hand, I proceeded to import it into VirtualBox, following the setup instructions provided on the Wazuh website. This step was akin to constructing a virtual security command center, ready to monitor my network.

![VirtualBox Import](https://i.imgur.com/T2zNYdp.png)

### First Log-In

Upon successful setup, I logged into the virtual machine using the default credentials: Username: `wazuh-user`, Password: `wazuh`. It was like stepping into the control room of my new digital security stronghold. I'll be sure to change this default password.

## Configuring Wazuh

### Finding the IP Address

To access the dashboard and connect to my Wazuh system, I used the command `ip a` to discover the IP address of my Wazuh server, which I duly noted down. This IP address served as the digital address for my security headquarters.

![IP Address](https://i.imgur.com/uXSlXIP.png)

### Navigating the Dashboard

With the IP address in hand, I opened my web browser and entered it, granting me access to the Wazuh dashboard. It felt like peering into the control screens of a vigilant security sentinel.

![Wazuh Dashboard](https://i.imgur.com/26xU0hY.png)

### Adding Security Agents

The heart of my SIEM system lay in adding security agents to monitor various devices on my network. To achieve this, I added an agent for both a Windows machine and a Mac.

#### Windows Agent

I utilized PowerShell to install and initiate the agent, empowering it to start its vigilant watch.

![Adding Windows Agent](https://i.imgur.com/Fv0ON8Y.png)

#### Mac Agent

With the Mac, I turned to the Terminal, configuring the agent to join my security team using the following command:

`curl -so wazuh-agent.pkg https://packages.wazuh.com/4.x/macos/wazuh-agent-4.5.2-1.intel64.pkg && sudo echo "WAZUH_MANAGER='<IP ADDRESS>' && WAZUH_AGENT_GROUP='default' && WAZUH_AGENT_NAME='<AGENT NAME>'" > /tmp/wazuh_envs && sudo installer -pkg ./wazuh-agent.pkg -target /`


## Observations and Early Alerts

After the setup was complete and both computers were under surveillance, I noticed some intriguing alerts. My SIEM system flagged vulnerabilities, such as the presence of the guest user not being disabled on the Mac. Additionally, I intentionally tested failed login attempts to see how the system responded. These early insights highlighted the power of proactive security monitoring.

## The Need for Time and Data

As I delved deeper into the world of SIEM, I recognized that the system's effectiveness would grow over time as it collected more data. I eagerly anticipated the wealth of knowledge and insights it would bring, allowing me to fine-tune my security protocols further.

## Future Explorations

My journey into the realm of home network security was far from over. The next step on my path to cybersecurity excellence involved setting up a honeypot, a fascinating endeavor I would delve into in a separate write-up. With each new experiment, my understanding of network security deepened, and I felt better equipped to safeguard my digital domain.

## Lessons Learned

This project taught me the importance of proactive security monitoring and the incredible potential that SIEM systems like Wazuh offer, even in a home network environment. It reinforced the notion that security is a journey, not a destination, and that each step taken brings greater resilience and knowledge.

![Alerts](insert-link-to-screenshot)

![Failed Login Attempts](insert-link-to-screenshot)

![Dashboard Insights](insert-link-to-screenshot)

My adventure in configuring Wazuh for home network security was just the beginning. It was a voyage of discovery, empowerment, and an unwavering commitment to the digital safety of my home.
