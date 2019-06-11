---
title: 'Lync Server 2013: Verificando a replicação de esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d115738a4f22cb7795c2eb5a00ac642fbe43fc77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="3f826-102">Verificando a replicação de esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f826-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f826-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="3f826-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="3f826-104">Antes de executar a preparação da floresta, verifique manualmente se a partição do esquema foi replicada.</span><span class="sxs-lookup"><span data-stu-id="3f826-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="3f826-105">Para verificar manualmente a replicação do esquema</span><span class="sxs-lookup"><span data-stu-id="3f826-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="3f826-106">Faça logon em um controlador de domínio como membro do grupo Administradores da empresa.</span><span class="sxs-lookup"><span data-stu-id="3f826-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="3f826-107">Para abrir editar ADSI, clique em **Iniciar**, em **Ferramentas administrativas**e em **ADSI Editar**.</span><span class="sxs-lookup"><span data-stu-id="3f826-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="3f826-108">Você também pode executar <STRONG>ADSIEdit. msc</STRONG> na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3f826-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="3f826-109">Na árvore do console de gerenciamento Microsoft (MMC), se ainda não estiver selecionado, clique em **ADSI Editar**.</span><span class="sxs-lookup"><span data-stu-id="3f826-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="3f826-110">No menu **Ação**, clique em **Conectar-se a**.</span><span class="sxs-lookup"><span data-stu-id="3f826-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="3f826-111">Na caixa de diálogo **Configurações de conexão** em **Selecione um Contexto de nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f826-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="3f826-112">No contêiner de esquema, procure por CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="3f826-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="3f826-113">Se esse objeto existir, e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **RangeLower** for 3, o esquema foi atualizado e replicado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="3f826-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="3f826-114">Se esse objeto não existir ou os valores dos atributos **rangeUpper** e **RangeLower** não forem especificados, o esquema não foi modificado ou não foi replicado.</span><span class="sxs-lookup"><span data-stu-id="3f826-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3f826-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="3f826-115">See Also</span></span>


[<span data-ttu-id="3f826-116">Executando preparação de esquema de Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f826-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="3f826-117">Preparando o esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f826-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

