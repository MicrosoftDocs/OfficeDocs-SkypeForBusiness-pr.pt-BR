---
title: 'Lync Server 2013: solução de problemas do plug-in do Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe652a2a378759584b8d855cdcdc7790b622ad02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518958"
---
# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="54b90-102">Solucionando problemas do plug-in do Lync VDI no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54b90-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54b90-103">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="54b90-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="54b90-104">Solucionando problemas com a instalação do plug-in do Lync VDI em um cliente fino</span><span class="sxs-lookup"><span data-stu-id="54b90-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="54b90-105">Caso existam problemas com a instalação de um plug-in VDI em um cliente fino, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="54b90-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="54b90-106">Assegure-se de que há espaço em disco suficiente na pasta que você especificou nas variáveis do sistema TEMP e TMP.</span><span class="sxs-lookup"><span data-stu-id="54b90-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="54b90-p101">Assegure-se de que a proteção contra gravação está desligada. Consulte a documentação do fabricante do seu dispositivo para instruções.</span><span class="sxs-lookup"><span data-stu-id="54b90-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="54b90-109">Solucionando problemas com pareamento</span><span class="sxs-lookup"><span data-stu-id="54b90-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="54b90-110">Quando o pareamento do plug-in VDI falha, o ícone de pareamento no canto inferior direito é exibido como um "X" vermelho, como mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="54b90-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="54b90-111">![Ícone do Lync VDI mostrando emparelhamento bem-sucedido](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Ícone do Lync VDI mostrando emparelhamento bem-sucedido")</span><span class="sxs-lookup"><span data-stu-id="54b90-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="54b90-112">A seguir estão possíveis razões para falhas e as ações corretivas que você pode tomar.</span><span class="sxs-lookup"><span data-stu-id="54b90-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="54b90-113">**O usuário inseriu credenciais incorretas durante a entrada.**</span><span class="sxs-lookup"><span data-stu-id="54b90-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="54b90-114">O usuário deve sair do Lync e entrar novamente com as credenciais corretas.</span><span class="sxs-lookup"><span data-stu-id="54b90-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="54b90-115">A caixa de diálogo de pareamento reaparecerá e mostrará se o pareamento teve êxito.</span><span class="sxs-lookup"><span data-stu-id="54b90-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="54b90-116">**Outra instância do cliente de área de trabalho remota está sendo executada.**</span><span class="sxs-lookup"><span data-stu-id="54b90-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="54b90-117">Se eles estiverem usando a conexão de área de trabalho remota no Windows, os usuários devem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="54b90-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="54b90-118">Iniciar o Gerenciador de Tarefas: pressionar **Alt+Ctrl+Delete**, e então clicar em **Iniciar Gerenciador de Tarefas**.</span><span class="sxs-lookup"><span data-stu-id="54b90-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="54b90-119">Clique na guia **Processos** e procure por todos os processos chamados **mstsc.exe** na lista.</span><span class="sxs-lookup"><span data-stu-id="54b90-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="54b90-120">Selecione cada processo **mstsc.exe** e então clique em **Finalizar Processo**.</span><span class="sxs-lookup"><span data-stu-id="54b90-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="54b90-121">Inicie uma nova sessão de área de trabalho remota e tente conectar novamente.</span><span class="sxs-lookup"><span data-stu-id="54b90-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="54b90-122">**Os arquivos necessários não foram instalados corretamente.**</span><span class="sxs-lookup"><span data-stu-id="54b90-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="54b90-123">Depois que o plug-in é instalado no computador local, os seguintes arquivos devem estar presentes em C: \\ arquivos de programa \\ Microsoft Office \\ Office15 (ou a letra de unidade apropriada):</span><span class="sxs-lookup"><span data-stu-id="54b90-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="54b90-124">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="54b90-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="54b90-125">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="54b90-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="54b90-126">Caso existam quaisquer problemas com o pareamento VDI, verifique para se assegurar que estes arquivos estão presentes no computador local.</span><span class="sxs-lookup"><span data-stu-id="54b90-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="54b90-127">**O cliente Lync está em execução no computador local.**</span><span class="sxs-lookup"><span data-stu-id="54b90-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="54b90-128">Para usar o plug-in do Lync VDI, um cliente do Lync não deve estar em execução no computador local, caso contrário, o emparelhamento falhará.</span><span class="sxs-lookup"><span data-stu-id="54b90-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="54b90-129">Como prática recomendada, o usuário não deve instalar um cliente Lync no computador local.</span><span class="sxs-lookup"><span data-stu-id="54b90-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

