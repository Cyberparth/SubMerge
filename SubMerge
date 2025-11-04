#!/bin/bash

# ========================================
# SubMerge : Automated Subdomain Recon Tool
# Author   : CyberParth
# Github   : https://github.com/Cyberparth
#=========================================

#=====Colours======
HIGH_INTENSITY_RED="\e[0;91m"
RED="\033[1;31m"
GREEN="\033[1;32m"
CYAN="\033[1;36m"
YELLOW="\033[1;33m"
NC="\033[0m"  #No Colour

#========ASCII BANNER===========
echo -e "${RED}"
#!/bin/bash

protocol=$(curl -s -I "https://$TARGET" | head -n 1 | grep -q "200" && echo "https" || echo "http")


#========ASCII BANNER===========
echo -e "${RED}"
cat << "EOF" 
                              
/ ___| _   _| |__ |  \/  | ___ _ __ __ _  ___ 
\___ \| | | | '_ \| |\/| |/ _ \ '__/ _` |/ _ \
 ___) | |_| | |_) | |  | |  __/ | | (_| |  __/
|____/ \__,_|_.__/|_|  |_|\___|_|  \__, |\___|
                                   |___/      
EOF
echo -e "${NC}"
echo -e "${YELLOW}        Author: CyberParth ${NC}"
echo -e "${CYAN}   Github: https://github.com/Cyberparth  ${NC}"


#CONFIG
TOOL_DIR="/usr/bin"
WORDLIST=$TOOL_DIR                           #  [to be updated not complete]

#ARG CHECK
if [ "$#" -ne 1 ]; then
    echo -e "${RED} Usage: $0 <target-domain(example.com)>${NC}"
    exit 1
fi


TARGET=$1
BASE_DIR=$(pwd)


echo -e "${HIGH_INTENSITY_RED}[*] Starting recon on: $TARGET${NC}"
echo -e "${HIGH_INTENSITY_RED}[*] Saving results in: $BASE_DIR${NC}"






#****************************************************************************************************
echo -e "${YELLOW}=============== AUTOMATING SUBDOMAIN ENUMERATION =============${NC}"
echo -e "${GREEN}Starting Subdomain Enumeration...${NC}"            

echo -e "${CYAN}[+]Subfinder is Running... ${NC}"
subfinder -d $TARGET -all -silent -o subfinder.txt 2>/dev/null 



echo -e "${CYAN}[+]Amass is Running... ${NC}"
amass enum -passive -d $TARGET -o amass_raw.txt 
grep -E "^[a-zA-Z0-9.-]+\$" amass_raw.txt > amass.txt 2>/dev/null
rm -fr amass_raw.txt                           #Raw data removed

echo -e "${CYAN}[+]Assetfinder is Running...${NC}"
assetfinder --subs-only $TARGET | grep -E "^[a-zA-Z0-9.-]+\$" > assetfinder.txt 2>/dev/null

# Merge and removing duplicate everything
echo -e "${CYAN}Merging and Removing Duplicates ${NC}"
cat *.txt | sort -u > unique_subdomains.txt
echo -e "${RED}Results are saved in unique_subdomains.txt ${NC}"
echo -e "${CYAN}[*] Total unique subdomains: $(wc -l < unique_subdomains.txt)${NC}"



 
