---
title: 'Lync Server 2013: problemas com o teste de ambiente'
description: 'Lync Server 2013: problemas com o teste de ambiente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551d7e914480e178e0558c1d17eefcf060c0688e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574967"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="05208-103">Problemas com o teste de ambiente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05208-103">Issues with the environment test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05208-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="05208-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="05208-105">O Best Practices Analyzer oferece uma maneira de verificar se o seu ambiente do Lync Server 2013 é uma configuração suportada.</span><span class="sxs-lookup"><span data-stu-id="05208-105">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="05208-106">Como parte da verificação de Serviços de Domínio do Active Directory, o analisador de práticas recomendadas realiza as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="05208-106">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="05208-107">Verifica os Serviços de Domínio Active Directory em preparo de esquema e floresta.</span><span class="sxs-lookup"><span data-stu-id="05208-107">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="05208-108">Identifica o número dos sites e domínios dos Serviços de Domínio Active Directory na implantação.</span><span class="sxs-lookup"><span data-stu-id="05208-108">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="05208-109">Verifica os níveis de floresta e domínio.</span><span class="sxs-lookup"><span data-stu-id="05208-109">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="05208-110">Verifica a versãod o controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="05208-110">Checks the domain controller version.</span></span>

  - <span data-ttu-id="05208-111">Identifica o domínio, a configuração e contexto de nomenclatura de esquema.</span><span class="sxs-lookup"><span data-stu-id="05208-111">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="05208-112">Identifica o número de usuários habilitados.</span><span class="sxs-lookup"><span data-stu-id="05208-112">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="05208-113">Verifica onde as definições globais dos Serviços de Domínio Active Directory estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="05208-113">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="05208-114">Verifica os pontos de conexão de serviço (SCPs) para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05208-114">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="05208-115">Identifica a versão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05208-115">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="05208-116">Resolve problemas com  oambiente</span><span class="sxs-lookup"><span data-stu-id="05208-116">Resolving Issues with the Environment</span></span>

<span data-ttu-id="05208-p102">Se o teste de ambiente encontrou problemas com seu ambiente, esses problemas são provavelmente causados por problemas com sua configuração do Active Directory ou o nível do software executando em servidores específicos. Por exemplo, se o analisador de práticas recomendadas identificar quaisquer controladores de domínio em seu ambiente executando Windows Server 2000, ele emitirá o aviso e você deverá atualizar os controladores de domínio para uma versão suportada do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="05208-p102">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers. For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

