---
title: Script do PowerShell para testar conexões de Controlador de Borda de Sessão de Roteamento Direto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este exemplo de script do PowerShell para testar as conexões do Controlador de Borda de Sessão de Roteamento Direto no Microsoft Teams.
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
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="a427b-103">Script do PowerShell para testar conexões de Controlador de Borda de Sessão de Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="a427b-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="a427b-104">O cliente de Teste SIP é um script do PowerShell de exemplo que você pode usar para testar conexões SBC (Controle de Borda de Sessão de Roteamento Direto) no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a427b-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="a427b-105">Este script testa a funcionalidade básica de um tronco SIP (Session Initiation Protocol) emparelhado ao cliente com Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="a427b-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="a427b-106">O script envia um teste SIP ao corredor de teste, aguarda o resultado e o apresenta em um formato acessível.</span><span class="sxs-lookup"><span data-stu-id="a427b-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="a427b-107">Você pode usar esse script para testar os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="a427b-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="a427b-108">Chamadas de entrada e saída</span><span class="sxs-lookup"><span data-stu-id="a427b-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="a427b-109">Toque simultâneo</span><span class="sxs-lookup"><span data-stu-id="a427b-109">Simultaneous ring</span></span>
- <span data-ttu-id="a427b-110">Escalonamento de mídia</span><span class="sxs-lookup"><span data-stu-id="a427b-110">Media escalation</span></span>
- <span data-ttu-id="a427b-111">Transferência consultiva</span><span class="sxs-lookup"><span data-stu-id="a427b-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="a427b-112">Baixar o script e a documentação</span><span class="sxs-lookup"><span data-stu-id="a427b-112">Download the script and documentation</span></span>

<span data-ttu-id="a427b-113">Baixe o [script e a documentação do cliente tester SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a427b-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a427b-114">O script do cliente SIP Tester dá suporte adal.ps versão 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="a427b-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="a427b-115">Um erro será retornado se uma versão posterior do adal.ps for usada.</span><span class="sxs-lookup"><span data-stu-id="a427b-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
