---
title: 'Lync Server 2013: Verificando a replicação de esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ea90012c116bb66caf16313d930c6f05db4413
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Verificando a replicação de esquema do Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Antes de executar a preparação da floresta, verifique manualmente se a partição do esquema foi replicada.

<div>

## <a name="to-manually-verify-schema-replication"></a>Para verificar manualmente a replicação do esquema

1.  Faça logon em um controlador de domínio como membro do grupo Administradores da empresa.

2.  Para abrir editar ADSI, clique em **Iniciar**, em **Ferramentas administrativas**e em **ADSI Editar**.
    
    <div>
    

    > [!TIP]  
    > Você também pode executar <STRONG>ADSIEdit. msc</STRONG> na linha de comando.

    
    </div>

3.  Na árvore do console de gerenciamento Microsoft (MMC), se ainda não estiver selecionado, clique em **ADSI Editar**.

4.  No menu **Ação**, clique em **Conectar-se a**.

5.  Na caixa de diálogo **Configurações de conexão** em **Selecione um Contexto de nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.

6.  No contêiner de esquema, procure por CN=ms-RTC-SIP-SchemaVersion. Se esse objeto existir, e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **RangeLower** for 3, o esquema foi atualizado e replicado com sucesso. Se esse objeto não existir ou os valores dos atributos **rangeUpper** e **RangeLower** não forem especificados, o esquema não foi modificado ou não foi replicado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Executando preparação de esquema de Active Directory no Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Preparando o esquema do Active Directory no Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

