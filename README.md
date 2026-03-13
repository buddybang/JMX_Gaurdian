# Step 1 — Generate the signed .lic for a 3-month client
java -jar tristha-license-tool.jar \
     --client "Jaywan Testing Services" --id JAYWAN-001 \
     --expiry 2026-06-13 --users 5 --out jaywan.lic

# Step 2 — Embed it in the product
cp jaywan.lic  sentinel-v61/src/main/resources/META-INF/tristha.lic

# Step 3 — Build and ship
cd sentinel-v61 && mvn clean package
# → deliver target/tristha-jmx-sentinel-*.jar
