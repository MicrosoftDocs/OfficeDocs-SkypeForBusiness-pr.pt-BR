---
title: 'Lync Server 2013: Atualizando da versão de avaliação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 703362f34c367d301e7d47e1bdc65f16a497ce88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="56df5-102">Atualizando da versão de avaliação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56df5-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56df5-103">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="56df5-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="56df5-104">Se você instalou a versão de avaliação do Microsoft Lync Server 2013, você precisará atualizar essa instalação uma cópia licenciada do software; Isso ocorre porque a versão de avaliação expira 180 dias após a instalação.</span><span class="sxs-lookup"><span data-stu-id="56df5-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="56df5-105">No entanto, não será necessário desinstalar completamente a versão de avaliação e instalar a versão licenciada.</span><span class="sxs-lookup"><span data-stu-id="56df5-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="56df5-106">Em vez disso, após obter uma chave de licenciamento válida, você poderá atualizar a versão de avaliação do Lync Server 2013 executando o procedimento a seguir em cada computador que atua como servidor front-end do Lync Server, diretor ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="56df5-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="56df5-107">Observe que você não precisa atualizar os computadores que executam outras funções de servidor, como um servidor de monitoramento ou servidor de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="56df5-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="56df5-108">Atualizando da versão de avaliação do Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56df5-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="56df5-109">Para atualizar um computador da versão de avaliação do Lync Server 2013 para a versão licenciada do software:</span><span class="sxs-lookup"><span data-stu-id="56df5-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="56df5-110">**Atualizando da versão de avaliação do Microsoft Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="56df5-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="56df5-111">Faça logon no computador como um administrador local.</span><span class="sxs-lookup"><span data-stu-id="56df5-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="56df5-112">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="56df5-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="56df5-113">No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="56df5-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="56df5-114">Talvez seja necessário especificar o caminho completo para o arquivo server.msi.</span><span class="sxs-lookup"><span data-stu-id="56df5-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="56df5-115">Esse arquivo pode ser encontrado na pasta instalação dos arquivos de instalação de mídia de volume do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56df5-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="56df5-116">Após a conclusão da instalação, digite o seguinte no prompt de comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="56df5-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="56df5-117">Repita esse procedimento em qualquer servidor front-end, diretor ou servidor de borda executando uma cópia de avaliação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56df5-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="56df5-118">Esse procedimento também deve ser executado em qualquer servidor de filial do escritório que tenha sido implantado usando os arquivos de instalação de mídia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56df5-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="56df5-119">Se você não tiver certeza se a versão de avaliação do Lync Server está sendo executada em um determinado computador, você pode verificar se está executando o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="56df5-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="56df5-120">O cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analisará o computador local e o relatará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="56df5-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="56df5-121">Que a chave de licença de volume do Lync Server foi instalada no computador, o que significa que nenhuma atualização é necessária.</span><span class="sxs-lookup"><span data-stu-id="56df5-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="56df5-122">A chave de licença de avaliação do Lync Server foi instalada, o que significa que o computador deve ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="56df5-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="56df5-p104">Que nenhuma chave de licença de volume é necessária no computador. A atualização da versão de avaliação para a versão licenciada só é necessária em servidores Front-End, Diretores e Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="56df5-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

