---
title: 'Lync Server 2013: Configurando senhas da conta de autenticação Kerberos'
description: 'Lync Server 2013: Configurando senhas da conta de autenticação Kerberos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577217"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="1e7c0-103">Configurando senhas da conta de autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e7c0-103">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e7c0-104">_**Última modificação do tópico:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-104">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="1e7c0-105">Depois de criar o objeto de computador para a conta de autenticação Kerberos, você poderá configurar a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="1e7c0-105">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="1e7c0-106">Execute o cmdlet do Windows PowerShell para configurar a senha da conta Kerberos em um servidor.</span><span class="sxs-lookup"><span data-stu-id="1e7c0-106">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="1e7c0-107">É possível definir a senha no objeto criado para a autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1e7c0-107">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="1e7c0-108">A senha pode ser definida como um valor conhecido, mas por padrão é uma senha aleatória.</span><span class="sxs-lookup"><span data-stu-id="1e7c0-108">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="1e7c0-109">A senha está disponível para todas as fontes de autenticação Kerberos que usam a conta.</span><span class="sxs-lookup"><span data-stu-id="1e7c0-109">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="1e7c0-110">Use os cmdlets do Windows PowerShell para configurar e gerenciar senhas de conta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1e7c0-110">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e7c0-111">O objeto de conta Kerberos é um objeto de computador, mas usa o parâmetro USERACCOUNT para operações nos cmdlets do Windows PowerShell referenciados.</span><span class="sxs-lookup"><span data-stu-id="1e7c0-111">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="1e7c0-112">Perceba que isso não é um erro, mas o comportamento pretendido do cmdlet quando usado com a criação e manutenção da conta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1e7c0-112">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e7c0-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1e7c0-113">In This Section</span></span>

  - [<span data-ttu-id="1e7c0-114">Definir uma senha de conta de autenticação Kerberos em um servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e7c0-114">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="1e7c0-115">Sincronizar uma senha de conta de autenticação Kerberos com o IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e7c0-115">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

