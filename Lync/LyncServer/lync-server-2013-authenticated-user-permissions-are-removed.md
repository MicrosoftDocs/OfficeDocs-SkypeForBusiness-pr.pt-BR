---
title: 'Lync Server 2013: as permissões de usuário autenticado são removidas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cf9f63fbe5340b3a241fc60b8623f54906dd8cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515758"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="ebbe9-102">As permissões de usuário autenticado são removidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebbe9-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebbe9-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ebbe9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ebbe9-104">Em um ambiente bloqueado do Active Directory, as ACEs (entradas de controle de acesso) de usuário autenticado são removidas dos contêineres padrão do Active Directory, incluindo Usuários, Configuração ou Sistema, e de unidades organizacionais em que objetos de Usuário e Computador estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="ebbe9-105">A remoção das ACEs de usuário autenticado impede o acesso de leitura às informações do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="ebbe9-106">No entanto, a remoção dos Ases cria problemas para o Lync Server 2013 porque ele depende das permissões de leitura desses contêineres para permitir que os usuários executem a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="ebbe9-p102">Nessa situação, o membro do grupo Admins. do Domínio, que é necessário para executar a preparação do domínio, a ativação do servidor e a criação de pool, não concede acesso de leitura às informações do Active Directory armazenadas em contêiners padrão. Você deve conceder manualmente as permissões de acesso de leitura em vários contêineres no domínio raiz da floresta para verificar se o procedimento de pré-requisito de preparação da floresta foi concluído.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-p102">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers. You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="ebbe9-109">Para permitir que um usuário execute a preparação do domínio, a ativação do servidor e a criação do pool em qualquer domínio raiz que não seja da floresta, você tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ebbe9-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="ebbe9-110">Use uma conta que seja membro do grupo Administradores de empresa para executar a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="ebbe9-111">Usar uma conta que seja membro do grupo Admins. do Domínio e conceder a essa conta permissões de acesso de leitura em cada um dos seguintes contêineres no domínio raiz da floresta:</span><span class="sxs-lookup"><span data-stu-id="ebbe9-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="ebbe9-112">Domínio</span><span class="sxs-lookup"><span data-stu-id="ebbe9-112">Domain</span></span>
    
      - <span data-ttu-id="ebbe9-113">Configuração ou Sistema</span><span class="sxs-lookup"><span data-stu-id="ebbe9-113">Configuration or System</span></span>

<span data-ttu-id="ebbe9-114">Se você não deseja usar uma conta que seja membro do grupo Administradores de Empresa para executar a preparação do domínio ou outras tarefas de instalação, conceda explicitamente acesso de leitura à conta que você deseja usar nos contêineres relevantes da raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="ebbe9-115">Para concecer permissões de acesso de leitura a usuários em contêineres do domínio raiz da floresta</span><span class="sxs-lookup"><span data-stu-id="ebbe9-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="ebbe9-116">Faça logon no computador associado ao domínio raiz da floresta com uma conta que seja membro do grupo Admins. do Domínio para o domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="ebbe9-117">Execute adsiedit.msc para o domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="ebbe9-118">Se as ACEs de usuário autenticado tiverem sido removidas do contêiner Domínio, Configuração ou Sistema, você deverá conceder permissões somente leitura no contêiner, conforme descrito nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="ebbe9-119">Clique com o botão direito do mouse no contêiner e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="ebbe9-120">Clique na guia **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="ebbe9-121">Clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="ebbe9-122">Na guia **Permissões**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="ebbe9-123">Digite o nome do usuário ou grupo permissões de recebimento usando o seguinte formato: `domain\account name` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="ebbe9-124">Na guia **Objetos**, em **Aplica-se a**, clique em **Somente Este Objeto**.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="ebbe9-125">Em **Permissões**, selecione as seguintes ACEs permitidas clicando na coluna **Permitir**: **Listar Conteúdo**, **Ler Todas as Propriedades** e **Permissões de Leitura**.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="ebbe9-126">Clique em **OK** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="ebbe9-127">Repita essas etapas para qualquer contêiner relevante listado na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="ebbe9-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

