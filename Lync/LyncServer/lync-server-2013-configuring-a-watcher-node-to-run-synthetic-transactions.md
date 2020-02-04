---
title: 'Lync Server 2013: Configurando um nó de inspetor para executar transações sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19211c786c288326d5769824524f5571e5df2f00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="0b6cd-102">Configurando um nó de inspetor para executar transações sintéticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b6cd-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b6cd-103">_**Tópico da última modificação:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="0b6cd-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="0b6cd-104">Após a instalação dos arquivos do agente do System Center, você deve configurar o próprio nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-104">After the System Center agent files have been installed, you must next configure the watcher node itself.</span></span> <span data-ttu-id="0b6cd-105">As etapas que você seguir para configurar um nó de Inspetor variam de acordo com o fato de o computador do nó do Inspetor estar dentro da sua rede de perímetro ou de fora da sua rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-105">The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="0b6cd-106">Ao configurar um nó do observador, você também deve escolher o tipo de método de autenticação a ser implantado neste nó.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="0b6cd-107">O Lync Server 2013 permite que você escolha um dos dois métodos de autenticação: servidor confiável ou autenticação de credenciais.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="0b6cd-108">As diferenças entre esses dois métodos são descritas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="0b6cd-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b6cd-109">Configuração</span><span class="sxs-lookup"><span data-stu-id="0b6cd-109">Configuration</span></span></th>
<th><span data-ttu-id="0b6cd-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="0b6cd-110">Description</span></span></th>
<th><span data-ttu-id="0b6cd-111">Locais com suporte</span><span class="sxs-lookup"><span data-stu-id="0b6cd-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b6cd-112">Servidor confiável</span><span class="sxs-lookup"><span data-stu-id="0b6cd-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="0b6cd-113">Usa uma certificação para personificar um servidor interno e desafios de autenticação de bypass.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="0b6cd-114">Isso é útil para administradores que preferem gerenciar um único certificado em vez de muitas senhas de usuário em cada nó de Inspetor.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="0b6cd-115">Dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="0b6cd-116">Observe que, com esse método, o nó do Inspetor deve estar no mesmo domínio que os pools sendo monitorados.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-116">Note that, with this method, the watcher node must be in the same domain as the pools being monitored.</span></span> <span data-ttu-id="0b6cd-117">Se o nó do Inspetor e os pools monitorados estiverem em domínios diferentes, use a autenticação de credenciais em vez disso.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-117">If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6cd-118">Autenticação de credenciais</span><span class="sxs-lookup"><span data-stu-id="0b6cd-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="0b6cd-119">Armazena os nomes de usuário e senhas com segurança no Gerenciador de Credencial do Windows no nó do observador.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="0b6cd-120">Esse modo requer mais gerenciamento de senha, mas é a única opção para nós de Inspetor localizados fora da empresa.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-120">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise.</span></span> <span data-ttu-id="0b6cd-121">Estes nós do observador não podem ser tratados como um ponto de extremidade confiável para autenticação.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-121">These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="0b6cd-122">Fora da empresa.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="0b6cd-123">Dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0b6cd-124">Você também deve verificar se o seu firewall tem regras de entrada para MonitoringHost. exe e PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="0b6cd-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="0b6cd-125">Se esses processos estiverem bloqueados pelo firewall, suas transações sintéticas falharão com um erro 504 (tempo limite do servidor).</span><span class="sxs-lookup"><span data-stu-id="0b6cd-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

