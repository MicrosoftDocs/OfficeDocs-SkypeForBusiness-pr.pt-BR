---
title: 'Lync Server 2013: verificando a replicação do esquema'
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
ms.openlocfilehash: e709e102af7b2f286361e0ad4c6323025d4a25e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Verificando a replicação do esquema do Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

Antes de executar a preparação da floresta, verifique manualmente se a partição do esquema foi replicada.

<div>

## <a name="to-manually-verify-schema-replication"></a>Para verificar manualmente a replicação do esquema

1.  Faça logon em um controlador de domínio como membro do grupo Administração de Empresa.

2.  Abra a Edição ADSI clicando em **Iniciar**, clicando em **Ferramentas Administrativas** e então em **Edição ADSI**.
    
    <div>
    

    > [!TIP]  
    > Como alternativa, você pode executar <STRONG>ADSIEdit. msc</STRONG> na linha de comando.

    
    </div>

3.  Na árvore do console de gerenciamento Microsoft (MMC), se ainda não estiver selecionada, clique em **edição ADSI**.

4.  No menu **Ação**, clique em **Conectar-se a**.

5.  Na caixa de diálogo **Configurações de Conexão** em **Selecione um Contexto de Nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.

6.  No contêiner de esquema, procure por CN=ms-RTC-SIP-SchemaVersion. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** for 3, o esquema terá sido atualizado e replicado com êxito. Caso o objeto não exista ou os valores dos atributos **rangeUpper** e **rangeLower** não são os especificados, então o esquema não foi modificado ou replicado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Executando a preparação do esquema do Active Directory no Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Preparando o esquema do Active Directory no Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

