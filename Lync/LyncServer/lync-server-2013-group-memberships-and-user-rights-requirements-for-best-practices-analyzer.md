---
title: Associações de grupo e requisitos de direitos de usuário para o analisador de práticas recomendadas
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
ms.openlocfilehash: b9561736fc6dce1649d0a3dd29e15a7d88500a38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="90379-102">Associações de grupo e requisitos de direitos de usuário para o analisador de práticas recomendadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90379-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90379-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="90379-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="90379-104">Para executar com êxito o analisador de práticas recomendadas, a conta de usuário que você usa para fazer logon deve ser um membro do grupo Administradores no computador local.</span><span class="sxs-lookup"><span data-stu-id="90379-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="90379-105">Além disso, para verificar seu ambiente, a conta de usuário deve ser um membro dos seguintes grupos:</span><span class="sxs-lookup"><span data-stu-id="90379-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="90379-106">**Administradores de domínio**   para enumerar as informações dos serviços de domínio Active Directory e para chamar os provedores de instrumentação de gerenciamento do Windows (WMI) nos controladores de domínio e nos servidores de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="90379-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="90379-107">**Os administradores**   são necessários em cada computador interno do Lync Server 2013 e em cada servidor de borda para chamar os provedores de instrumentação de gerenciamento do Windows (WMI) e acessar o registro.</span><span class="sxs-lookup"><span data-stu-id="90379-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="90379-108">**RTCUniversalReadOnlyAdmins**   direitos administrativos do Lync Server 2013, completos ou delegados, somente leitura.</span><span class="sxs-lookup"><span data-stu-id="90379-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="90379-109">**Modo de exibição do Exchange somente administrador**   completo ou delegado modo de exibição do Exchange somente administrador na organização do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="90379-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="90379-110">Se a sua conta de usuário não tiver direitos de usuário suficientes, você terá duas opções:</span><span class="sxs-lookup"><span data-stu-id="90379-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="90379-111">Em um prompt de comando, use o comando **runas** para executar a ferramenta em uma conta que tem direitos de usuário suficientes.</span><span class="sxs-lookup"><span data-stu-id="90379-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="90379-112">A sintaxe é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="90379-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="90379-113">Na página **conectar-se ao Active Directory** , defina as credenciais das contas que você planeja usar para executar o analisador de práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="90379-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="90379-114">Clique em **Mostrar opções avançadas de login**.</span><span class="sxs-lookup"><span data-stu-id="90379-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="90379-115">Você pode inserir três contas: uma para conectar-se aos serviços de domínio do Active Directory, uma para conexão com servidores de borda do Lync Server 2013 e outra para conexão com os servidores Exchange.</span><span class="sxs-lookup"><span data-stu-id="90379-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="90379-116">Se você não especificar nenhuma dessas contas, a conta de usuário que você usou para fazer logon e executar o analisador de práticas recomendadas será usada.</span><span class="sxs-lookup"><span data-stu-id="90379-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

