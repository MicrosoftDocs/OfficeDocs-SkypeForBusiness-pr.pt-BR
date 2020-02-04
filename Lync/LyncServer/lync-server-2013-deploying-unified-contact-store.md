---
title: 'Lync Server 2013: Implantando repositório unificado de contatos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d224ec7a9c452c45f9f3471403301460a2a31cc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="2f3e3-102">Implantando repositório unificado de contatos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f3e3-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f3e3-103">_**Tópico da última modificação:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="2f3e3-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="2f3e3-104">Habilitar o repositório de contatos unificado no Lync Server 2013 não requer nenhuma configuração de topologia.</span><span class="sxs-lookup"><span data-stu-id="2f3e3-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="2f3e3-105">Habilitar o repositório de contatos unificado para usuários requer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f3e3-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="2f3e3-106">Que a política do repositório unificado de contatos esteja habilitada (ela é habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="2f3e3-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="2f3e3-107">Os usuários fazem logon com o Lync 2013 pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="2f3e3-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="2f3e3-108">Após a migração dos contatos de um usuário, o que acontece automaticamente quando um usuário faz logon com o Lync 2013, o usuário pode acessar e gerenciar seus contatos do Lync do Lync 2013, Outlook 2013 ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="2f3e3-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="2f3e3-109">O usuário não precisa estar conectado ao Lync para gerenciar seus contatos do Outlook ou do Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="2f3e3-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f3e3-110">Se um usuário fizer logon do Lync 2010 após a migração, os contatos e os grupos estarão disponíveis e atualizados, mas o usuário não poderá gerenciar (ou seja, adicionar, excluir, mover, marcar, remover ou modificar) esses contatos.</span><span class="sxs-lookup"><span data-stu-id="2f3e3-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2f3e3-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2f3e3-111">In This Section</span></span>

  - [<span data-ttu-id="2f3e3-112">Habilitar usuários para repositório unificado de contatos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f3e3-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="2f3e3-113">Migrar usuários para o repositório unificado de contatos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f3e3-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="2f3e3-114">Reverter usuários migrados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f3e3-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

