---
title: 'Lync Server 2013: Configurando um nó do inspetor para executar transações sintéticas'
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
ms.openlocfilehash: b3314116f150b0bb266f08919746fb61c65bc682
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="442b5-102">Configurando um nó do inspetor para executar transações sintéticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="442b5-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="442b5-103">_**Última modificação do tópico:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="442b5-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="442b5-p101">Após os arquivos do agente do Centro do Sistema terem sido instalados, você deve configurar o nó do observador sozinho. As etapas realizadas para configurar um nó do observador irá variar dependendo se seu computador do nó do observador está dentro da sua rede de perímetro ou fora.</span><span class="sxs-lookup"><span data-stu-id="442b5-p101">After the System Center agent files have been installed, you must next configure the watcher node itself. The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="442b5-106">Ao configurar um nó do observador, você também deve escolher o tipo de método de autenticação a ser implantado neste nó.</span><span class="sxs-lookup"><span data-stu-id="442b5-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="442b5-107">O Lync Server 2013 permite que você escolha um dos dois métodos de autenticação: servidor confiável ou autenticação de credencial.</span><span class="sxs-lookup"><span data-stu-id="442b5-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="442b5-108">As diferenças entre estes dois métodos são destacadas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="442b5-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="442b5-109">Configuração</span><span class="sxs-lookup"><span data-stu-id="442b5-109">Configuration</span></span></th>
<th><span data-ttu-id="442b5-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="442b5-110">Description</span></span></th>
<th><span data-ttu-id="442b5-111">Locais suportados</span><span class="sxs-lookup"><span data-stu-id="442b5-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="442b5-112">Servidor confiável</span><span class="sxs-lookup"><span data-stu-id="442b5-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="442b5-113">Usa uma certificação para personificar um servidor interno e desafios de autenticação de bypass.</span><span class="sxs-lookup"><span data-stu-id="442b5-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="442b5-114">Isto é útil para os administradores que preferem gerenciar um único certificado ao invés de várias senhas do usuário no nó do observador.</span><span class="sxs-lookup"><span data-stu-id="442b5-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="442b5-115">Dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="442b5-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="442b5-p103">Observe que, com este método, o nó do observador deve estar no mesmo domínio que os pools sendo monitorados. Se o nó do observador e os pools monitorados estão em domínios diferentes, use a Autenticação de Credencial.</span><span class="sxs-lookup"><span data-stu-id="442b5-p103">Note that, with this method, the watcher node must be in the same domain as the pools being monitored. If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="442b5-118">Autenticação de Credencial</span><span class="sxs-lookup"><span data-stu-id="442b5-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="442b5-119">Armazena os nomes de usuário e senhas com segurança no Gerenciador de Credencial do Windows no nó do observador.</span><span class="sxs-lookup"><span data-stu-id="442b5-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="442b5-p104">Este modo exige mais gerenciamento de senha, mas é a única opção para nós do observador fora da empresa. Estes nós do observador não podem ser tratados como um ponto de extremidade confiável para autenticação.</span><span class="sxs-lookup"><span data-stu-id="442b5-p104">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise. These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="442b5-122">Fora da empresa.</span><span class="sxs-lookup"><span data-stu-id="442b5-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="442b5-123">Dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="442b5-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="442b5-124">Você também deve verificar se o firewall tem regras de entrada para MonitoringHost. exe e PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="442b5-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="442b5-125">Se esses processos forem bloqueados pelo firewall, suas transações sintéticas falharão com o erro 504 (tempo limite do servidor).</span><span class="sxs-lookup"><span data-stu-id="442b5-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

