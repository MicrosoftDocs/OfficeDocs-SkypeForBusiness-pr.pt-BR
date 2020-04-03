---
title: Script do PowerShell para testar conexões do controlador de borda de sessão de roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este exemplo de script do PowerShell para testar as conexões de controlador de borda de sessão de roteamento direto no Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 344bf59d401e43c40c6f643b334c2f34311d6cbe
ms.sourcegitcommit: 8665603fae8408ccbc083dd59cb01936ebe96c58
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116687"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="cbb1b-103">Script do PowerShell para testar conexões do controlador de borda de sessão de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="cbb1b-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="cbb1b-104">O cliente testador SIP é um exemplo de script do PowerShell que você pode usar para testar as conexões de SBC (controlador de borda de sessão de roteamento direto) no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cbb1b-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="cbb1b-105">Este script testa a funcionalidade básica de um tronco SIP (protocolo de iniciação de sessão) emparelhado ao cliente com roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="cbb1b-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="cbb1b-106">O script envia um teste SIP para o executor do teste, aguarda o resultado e o apresenta em um formato legível por pessoas.</span><span class="sxs-lookup"><span data-stu-id="cbb1b-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="cbb1b-107">Você pode usar esse script para testar os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="cbb1b-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="cbb1b-108">Chamadas de entrada e de saída</span><span class="sxs-lookup"><span data-stu-id="cbb1b-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="cbb1b-109">Toque simultâneo</span><span class="sxs-lookup"><span data-stu-id="cbb1b-109">Simultaneous ring</span></span>
- <span data-ttu-id="cbb1b-110">Escalonamento de mídia</span><span class="sxs-lookup"><span data-stu-id="cbb1b-110">Media escalation</span></span>
- <span data-ttu-id="cbb1b-111">Transferência consultiva</span><span class="sxs-lookup"><span data-stu-id="cbb1b-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="cbb1b-112">Baixar o script e a documentação</span><span class="sxs-lookup"><span data-stu-id="cbb1b-112">Download the script and documentation</span></span>

<span data-ttu-id="cbb1b-113">Baixe o [script e a documentação do cliente de teste SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="cbb1b-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="cbb1b-114">O script do cliente testador SIP suporta apenas a versão adal.ps do 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="cbb1b-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="cbb1b-115">Um erro será retornado se uma versão mais recente do adal.ps for usada.</span><span class="sxs-lookup"><span data-stu-id="cbb1b-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
