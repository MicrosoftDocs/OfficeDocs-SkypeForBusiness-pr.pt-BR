---
title: Migrar os números de acesso discado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fcc5b7dac5c9769d92afc86e7036f7e410f2278
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrar os números de acesso discado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-26_

Migrar números de acesso de discagem requer duas etapas: executar o cmdlet **Import-CsLegacyConfiguration** (concluído anteriormente em [importar políticas e configurações](import-policies-and-settings.md)) para migrar planos de discagem e outras configurações de número de acesso de discagem, e executar o cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Para migrar os números de acesso de discagem

1.  Abra a ferramenta administrativa do Office Communications Server 2007 R2.

2.  Na árvore do console, clique com o botão direito do mouse no nó de floresta, clique em **Propriedades** e, em seguida, clique em **Propriedades do Atendedor de Conferência**.

3.  Na guia **Números de Telefone de Acesso**, clique em **Atendido pelo Pool** para classificar os números de telefone de acesso pelo pool associado e identificar todos os números de acesso para o pool a partir do qual você está migrando.

4.  Para identificar URI do SIP para cada número de acesso de discagem, clique duas vezes no número de acesso para abrir a caixa de seleção **Editar Número do Atendedor de Conferência** e verifique **URI do SIP**.

5.  Abra o Shell de Gerenciamento do Lync Server.

6.  Para mover cada número de acesso de discagem para um pool hospedado no Lync Server 2013, execute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Na ferramenta administrativa do Office Communications Server 2007 R2, na guia **números de telefone de acesso** , verifique se os números de acesso de discagem permanecem para o pool do Office Communications Server 2007 R2 a partir do qual você está migrando.

</div>

</div>

<span> </span>

</div>

</div>

</div>

