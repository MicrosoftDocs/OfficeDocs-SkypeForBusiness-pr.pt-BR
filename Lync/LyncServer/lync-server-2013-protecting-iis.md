---
title: 'Lync Server 2013: protegendo o IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d53797c490ba53872786311b51e310e6400addf5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="48174-102">Protegendo o IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48174-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48174-103">_**Última modificação do tópico:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="48174-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="48174-104">No Microsoft Office Communications Server 2007 e no Microsoft Office Communications Server 2007 R2, o IIS (serviços de informações da Internet) é executado sob uma conta de usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="48174-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="48174-105">Isso poderia causar problemas: se a senha tiver expirado, você poderia perder os Serviços Web, um problema que geralmente era difícil de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="48174-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="48174-106">Para ajudar a evitar o problema de expirar senhas, o Microsoft Lync Server 2013 permite que você crie uma conta de computador (para um computador que não existe realmente) que possa servir como a entidade de autenticação para todos os computadores em um site que executa o IIS.</span><span class="sxs-lookup"><span data-stu-id="48174-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="48174-107">Como essas contas utilizam o protocolo de autenticação Kerberos, elas são referidas como contas Kerberos e o novo processo de autenticação é conhecido como autenticação Kerberos de Web.</span><span class="sxs-lookup"><span data-stu-id="48174-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="48174-108">Isso permite que você gerencie todos seus servidores IIS usando uma única conta.</span><span class="sxs-lookup"><span data-stu-id="48174-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="48174-109">Para executar os servidores sob essa entidade de autenticação, primeiro você deve criar uma conta de computador usando o cmdlet New-CsKerberosAccount; essa conta é então atribuída a um ou mais sites.</span><span class="sxs-lookup"><span data-stu-id="48174-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="48174-110">Após a atribuição ter sido feita, a associação entre a conta e o site do Lync Server 2013 será habilitada executando o cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="48174-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="48174-111">Entre outras coisas, isso cria o SPN (nome da entidade de serviço) no AD DS (Serviços de Domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="48174-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="48174-112">Os SPNs fornecem uma maneira para os aplicativos cliente localizarem um determinado serviço.</span><span class="sxs-lookup"><span data-stu-id="48174-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="48174-113">Para obter detalhes, consulte [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) na documentação de Operações.</span><span class="sxs-lookup"><span data-stu-id="48174-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="48174-114">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="48174-114">Best Practices</span></span>

<span data-ttu-id="48174-p103">Para ajudar a aumentar a segurança do IIS, recomendamos que você implemente uma conta Kerberos para o IIS. Se você não implementar uma conta Kerberos, o IIS será executado sob uma conta de usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="48174-p103">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS. If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

