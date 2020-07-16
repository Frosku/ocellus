# Ocellus

**NOTE: Everything below is subject to change. This is an early-stage project
with early-stage ideas, and it may turn out that there are better ways to
achieve the desired goals.**

## Design Goals of Ocellus

Ocellus is a *work-in-progress* decentralized image archiving network which
strives to be resistant to censorship and targeted attacks. The stated goals
of the project are:

- **Federated** - users on one Ocellus instance can search for, comment on,
favorite, and upload images to other Ocellus instances;
- **Open** - Ocellus should be based on open protocols, to allow for alternative
code bases to be rapidly developed;
- **Resilient** - no amount of mob pressure or bad actors should be able to
bring down the network or render it inoperable;
- **Censorship-resistant** - By the nature of it being a decentralized network,
no operator should be able to censor the network;
- **Tailored** - operators can run their own nodes with as few or as many rules
as they see fit, to tailor those nodes to their own community's preferences;
- **Easy to use** - an end-user should not have to understand how the network
operates to use it.

## How Does It Work?

The Ocellus network is made up of nodes. These can run the official Ocellus 
codebase, or any other codebase compliant with the Ocellus open protocol, 
which is likely to be based on 
[WebTorrent](https://github.com/webtorrent/webtorrent/blob/master/docs/api.md)
and
[ActivityPub](https://www.w3.org/TR/activitypub/#follow-activity-inbox), open
standards designed to enable easier communication between decentralized
applications.

There will be two primary types of node: community nodes (also known as Booru
nodes), and seed nodes (also known as Image nodes). Operators can choose to run
one, the other, or both.

Community nodes will be federated together, and will be responsible for the
community layer. Each community node will have the ability to determine its 
own rules as to what images can be uploaded, how those images should be tagged,
and which other community nodes it wants to federate with. Operators will have
full control over their own community nodes.

Most users will register on a single Ocellus community node and use that 
community node for all of their interactions with the network, including 
searching for, commenting on, and uploading images to other community nodes.

Image nodes will be fully decentralized, and will serve image files. When a
user finds an image they want to view on a community node, that image will be
downloaded transparently via webtorrent and presented on the user interface 
of the community node.

Image torrents will be de-duped via their hash. If a user uploads an image
which does not already exist on the Ocellus network to a community node, that
image will be transparently converted into a torrent file and the user will
seed the image until it reaches saturation point. If a user uploads an image
which already exists on the network, the community node will locate the
existing torrent via its hash, and will immediately begin serving the image.

It is my belief that this coupling of federated community and peer-to-peer
file sharing offers the most power to users, whilst also allowing for some
moderation of community nodes (for example, a community node focused around
pictures of trains will not have to show furry art in its search results).
As running a node will not require the storage or traffic requirements to
store the entire image library, this model is also incredibly friendly to
Operators with less financial resources.

## Usage

N/A. No functionality is implemented.
