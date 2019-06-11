---
title: Migrar números de acesso de discagem
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrar números de acesso de discagem

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-26_

A migração de números de acesso discado requer duas etapas: executando o cmdlet **Import-CsLegacyConfiguration** (concluído anteriormente nas [políticas e configurações de importação](import-policies-and-settings.md)) para migrar planos de discagem e outras configurações de número de acesso à discagem e executar o ** Cmdlet Move-CsApplicationEndpoint** para migrar os objetos de contato.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Para migrar números de acesso de discagem

1.  Abra a ferramenta administrativa do Office Communications Server 2007 R2.

2.  Na árvore do console, clique com o botão direito do mouse no nó da floresta, clique em **Propriedades**e, em seguida, clique em **Propriedades do atendedor de conferência**.

3.  Na guia **números de telefone do Access** , clique em **atendido por pool** para classificar os números de telefone de acesso pelo pool associado e identificar todos os números de acesso do pool do qual você está migrando.

4.  Para identificar o URI SIP para cada número de acesso, clique duas vezes no número de acesso para abrir a caixa de diálogo **Editar número** de atendedor de conferência e procure por **URI de SIP**.

5.  Abra o Shell de gerenciamento do Lync Server.

6.  Para mover cada número de acesso à discagem para um pool hospedado no Lync Server 2013, execute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Na ferramenta administrativa do Office Communications Server 2007 R2, na guia **números de telefone do Access** , verifique se nenhum número de acesso de discagem permanece para o pool do Office Communications Server 2007 R2 do qual você está migrando.

</div>

</div>

<span> </span>

</div>

</div>

</div>

