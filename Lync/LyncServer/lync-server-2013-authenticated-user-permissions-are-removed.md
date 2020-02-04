---
title: 'Lync Server 2013: Permissões de usuário autenticado são removidas'
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
ms.openlocfilehash: 63b9761f96156fdc4dea124d4438cdb8685add26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="80a92-102">Permissões de usuário autenticado são removidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80a92-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80a92-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="80a92-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="80a92-104">Em um ambiente do Active Directory bloqueado, as entradas de controle de acesso (ACEs) do usuário autenticado são removidas dos recipientes padrão do Active Directory, incluindo os usuários, a configuração ou o sistema e as unidades organizacionais (UOs) em que o usuário e o computador objetos são armazenados.</span><span class="sxs-lookup"><span data-stu-id="80a92-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="80a92-105">A remoção de ACEs de usuários autenticados impede o acesso de leitura às informações do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="80a92-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="80a92-106">No entanto, a remoção das ACEs cria problemas para o Lync Server 2013 porque depende das permissões de leitura para esses contêineres para permitir que os usuários executem a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="80a92-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="80a92-107">Nessa situação, a associação no grupo Domain admins, que é necessária para executar a preparação do domínio, a ativação do servidor e a criação de pool, não concede mais acesso de leitura às informações do Active Directory armazenadas nos contêineres padrão.</span><span class="sxs-lookup"><span data-stu-id="80a92-107">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="80a92-108">Você deve conceder manualmente permissões de acesso de leitura em vários recipientes do domínio raiz da floresta para verificar se o procedimento de preparação da floresta de pré-requisito está concluído.</span><span class="sxs-lookup"><span data-stu-id="80a92-108">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="80a92-109">Para permitir que um usuário execute a preparação do domínio, a ativação do servidor ou a criação de pool em qualquer domínio raiz que não seja da floresta, você tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="80a92-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="80a92-110">Use uma conta que seja um membro do grupo Administradores da empresa para executar a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="80a92-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="80a92-111">Use uma conta que seja um membro do grupo Domain admins e conceda esta conta às permissões de leitura de conta em cada um dos seguintes recipientes no domínio raiz da floresta:</span><span class="sxs-lookup"><span data-stu-id="80a92-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="80a92-112">Domínio</span><span class="sxs-lookup"><span data-stu-id="80a92-112">Domain</span></span>
    
      - <span data-ttu-id="80a92-113">Configuração ou sistema</span><span class="sxs-lookup"><span data-stu-id="80a92-113">Configuration or System</span></span>

<span data-ttu-id="80a92-114">Se você não quiser usar uma conta que seja membro do grupo Administradores da empresa para executar a preparação do domínio ou outras tarefas de configuração, conceda explicitamente à conta que você deseja usar o acesso de leitura nos contêineres relevantes na raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="80a92-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="80a92-115">Para conceder aos usuários permissões de acesso de leitura em contêineres no domínio raiz da floresta</span><span class="sxs-lookup"><span data-stu-id="80a92-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="80a92-116">Faça logon no computador associado ao domínio raiz da floresta com uma conta que seja membro do grupo Domain admins do domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="80a92-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="80a92-117">Execute ADSIEdit. msc para o domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="80a92-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="80a92-118">Se as ACEs do usuário autenticado tiverem sido removidas do contêiner de domínio, configuração ou sistema, você deverá conceder permissões somente leitura para o contêiner, conforme descrito nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="80a92-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="80a92-119">Clique com o botão direito do mouse no contêiner e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="80a92-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="80a92-120">Clique na guia **segurança** .</span><span class="sxs-lookup"><span data-stu-id="80a92-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="80a92-121">Clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="80a92-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="80a92-122">Na guia **permissões** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80a92-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="80a92-123">Digite o nome do usuário ou do grupo permissões de recebimento usando o seguinte formato: `domain\account name`e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="80a92-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="80a92-124">Na guia **objetos** , em **aplica-se a**, clique **somente neste objeto**.</span><span class="sxs-lookup"><span data-stu-id="80a92-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="80a92-125">Em **permissões**, selecione as seguintes ACEs de permissão clicando no botão **permitir** coluna: **listar o conteúdo**, **ler todas as propriedades**e **ler permissões**.</span><span class="sxs-lookup"><span data-stu-id="80a92-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="80a92-126">Clique em **OK** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="80a92-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="80a92-127">Repita essas etapas para qualquer um dos recipientes relevantes listados na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="80a92-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

