# Dev Setup for IRS

This repo is used for development setup of the IRS. It uses vscode remote containers. Therefore as a prerequisite you need to have a running docker instance and a up-to-date vscode instance (not the open-source one).

The setup used in the repo is based on this [GitHub issue](https://github.com/microsoft/vscode-remote-release/issues/254) and follows the description in [this comment](https://github.com/microsoft/vscode-remote-release/issues/254#issuecomment-491124819). Basically there is one docker-compose file in the root of this repo. Backend and Frontend are included via sub-modules (you need to check them out and update to the latest commit for development). Both repos have a .devcontainer.json file in the root folder that points to the docker-compose file mentioned before. The docker-compose also includes the other services needed (eg rabbitmq and a db).

To start the containers do the following:

* start vscode and open Backend folder
* vscode should ask you whether you want to re-open the folder in a remote container. If it doesnt hit `SHIFT+Crtl+p` and search for `Remote-containers: rebuild Container`. That should build the needed containers.
* open another window and open the `Frontend` folder. Hit again `SHIFT+Crtl+p` and search for `Remote-Containers: Attach to running container` . vscode should attach the new window to the already built frontend container