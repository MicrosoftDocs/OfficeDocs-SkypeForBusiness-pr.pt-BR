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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9910ac347b5e797ad30ac65e76173ba4024a87c4
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547235"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="7aefc-103">Script do PowerShell para testar conexões do controlador de borda de sessão de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="7aefc-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="7aefc-104">O cliente testador SIP é um exemplo de script do PowerShell que você pode usar para testar as conexões de SBC (controlador de borda de sessão de roteamento direto) no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7aefc-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="7aefc-105">Este script testa a funcionalidade básica de um tronco SIP (protocolo de iniciação de sessão) emparelhado ao cliente com roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="7aefc-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="7aefc-106">O script envia um teste SIP para o executor do teste, aguarda o resultado e o apresenta em um formato legível por pessoas.</span><span class="sxs-lookup"><span data-stu-id="7aefc-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="7aefc-107">Você pode usar esse script para testar os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="7aefc-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="7aefc-108">Chamadas de entrada e de saída</span><span class="sxs-lookup"><span data-stu-id="7aefc-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="7aefc-109">Toque simultâneo</span><span class="sxs-lookup"><span data-stu-id="7aefc-109">Simultaneous ring</span></span>
- <span data-ttu-id="7aefc-110">Escalonamento de mídia</span><span class="sxs-lookup"><span data-stu-id="7aefc-110">Media escalation</span></span>
- <span data-ttu-id="7aefc-111">Transferência consultiva</span><span class="sxs-lookup"><span data-stu-id="7aefc-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="7aefc-112">Baixar o script e a documentação</span><span class="sxs-lookup"><span data-stu-id="7aefc-112">Download the script and documentation</span></span>

<span data-ttu-id="7aefc-113">Baixe o [script e a documentação do cliente de teste SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="7aefc-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>