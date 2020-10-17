---
title: Associações de grupo e requisitos de direitos do usuário para o analisador de práticas recomendadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1a72a7fdc73aeda96a2875ac48fd51b6023ddba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506068"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="87ad8-102">Associações de grupo e requisitos de direitos do usuário para o analisador de práticas recomendadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87ad8-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87ad8-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="87ad8-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="87ad8-p101">Para executar com êxito o Analisador de Práticas Recomendadas, a conta de usuário utilizada para fazer login deve ser membro do grupo Administradores no computador local. Além disso, para verificar o seu ambiente, a conta de usuário deve ser membro dos seguintes grupos:</span><span class="sxs-lookup"><span data-stu-id="87ad8-p101">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer. Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="87ad8-106">**Administradores**     de domínio Para enumerar as informações dos serviços de domínio do Active Directory e chamar os provedores de instrumentação de gerenciamento do Windows (WMI) nos controladores de domínio e servidores de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="87ad8-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="87ad8-107">**Os administradores**     Obrigatório em cada computador interno do Lync Server 2013 e em cada servidor de borda para chamar os provedores de instrumentação de gerenciamento do Windows (WMI) e acessar o registro.</span><span class="sxs-lookup"><span data-stu-id="87ad8-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="87ad8-108">**RTCUniversalReadOnlyAdmins**     Direitos administrativos de somente leitura do Lync Server 2013, completo ou delegado.</span><span class="sxs-lookup"><span data-stu-id="87ad8-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="87ad8-109">Administrador somente para **exibição do Exchange**     Administrador somente para exibição do Exchange completo ou delegado na organização do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="87ad8-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="87ad8-110">Se a sua conta de usuário não tem os direitos de usuário suficientes, você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="87ad8-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="87ad8-111">No prompt de comandos, use o comando **runas** para executar a ferramenta na conta com direitos de usuários suficientes.</span><span class="sxs-lookup"><span data-stu-id="87ad8-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="87ad8-112">A sintaxe é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="87ad8-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="87ad8-113">Na página **Conectar-se ao Active Directory**, defina as credenciais das contas que planeja usar para executar o Analisador de Práticas Recomendadas.</span><span class="sxs-lookup"><span data-stu-id="87ad8-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="87ad8-114">Clique em **Mostrar opções de login avançadas**.</span><span class="sxs-lookup"><span data-stu-id="87ad8-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="87ad8-115">Você pode inserir três contas: uma para conectar-se aos serviços de domínio do Active Directory, uma para conexão com os servidores de borda do Lync Server 2013 e outra para conexão com os servidores do Exchange.</span><span class="sxs-lookup"><span data-stu-id="87ad8-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="87ad8-116">Se você não especificar nenhuma destas contas, a conta do usuário utilizada para fazer login e executar o Analisador de Práticas Recomendadas é usada.</span><span class="sxs-lookup"><span data-stu-id="87ad8-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

