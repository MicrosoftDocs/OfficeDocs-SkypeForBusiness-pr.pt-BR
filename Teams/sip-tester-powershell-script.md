---
title: Script do PowerShell para testar conexões do Controlador de Borda de Sessão de Roteamento Direto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este exemplo de script do PowerShell para testar conexões de Controlador de Borda de Sessão de Roteamento Direto Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834271"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="a9650-103">Script do PowerShell para testar conexões do Controlador de Borda de Sessão de Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="a9650-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="a9650-104">O cliente do Testador SIP é um script do PowerShell de exemplo que você pode usar para testar conexões SBC (Direct Routing Session Border Controller) no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a9650-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="a9650-105">Este script testa a funcionalidade básica de um tronco SIP (Protocolo de Iniciação de Sessão) emparelhado ao cliente com Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="a9650-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="a9650-106">O script envia um teste SIP para o testador, aguarda o resultado e o apresenta em um formato acessível para humanos.</span><span class="sxs-lookup"><span data-stu-id="a9650-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="a9650-107">Você pode usar esse script para testar os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="a9650-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="a9650-108">Chamadas de saída e de entrada</span><span class="sxs-lookup"><span data-stu-id="a9650-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="a9650-109">Anel simultâneo</span><span class="sxs-lookup"><span data-stu-id="a9650-109">Simultaneous ring</span></span>
- <span data-ttu-id="a9650-110">Escalonamento de mídia</span><span class="sxs-lookup"><span data-stu-id="a9650-110">Media escalation</span></span>
- <span data-ttu-id="a9650-111">Transferência consultiva</span><span class="sxs-lookup"><span data-stu-id="a9650-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="a9650-112">Baixar o script e a documentação</span><span class="sxs-lookup"><span data-stu-id="a9650-112">Download the script and documentation</span></span>

<span data-ttu-id="a9650-113">Baixe o [script e a documentação do cliente do Testador SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a9650-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a9650-114">O script de cliente do testador SIP só dá suporte adal.ps versão 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="a9650-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="a9650-115">Um erro será retornado se uma versão posterior do adal.ps for usada.</span><span class="sxs-lookup"><span data-stu-id="a9650-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
