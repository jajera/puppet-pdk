# puppet-pdk

## commands

pdk new module webserver

cd webserver

pdk new class webserver

pdk validate

pdk test unit --parallel

pdk bundle install

pdk bundle exec rake 'litmus:provision[docker, litmusimage/debian:10]'
pdk bundle exec rake 'litmus:provision[docker, litmusimage/redhat:8]'

pdk bundle exec rake litmus:install_agent

bolt command run 'puppet --version' --targets localhost:2222 --inventoryfile spec/fixtures/litmus_inventory.yaml

pdk bundle exec rake litmus:install_module

bolt command run 'puppet module list' --targets localhost:2222 -i spec/fixtures/litmus_inventory.yaml

pdk bundle exec rake litmus:acceptance:parallel

pdk bundle exec rake litmus:tear_down
