---
title: 'Lync Server 2013: criar ou modificar um objeto de contato de telefone de área comum'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e9e7ddf1a4911b9afb3428531911223f62ea723
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Criar ou modificar um objeto de contato de telefone de área comum no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-20_

Para criar objetos de contato dos serviços de domínio Active Directory para todos os seus telefones de área comuns, use o cmdlet **New-CsCommonAreaPhone** . Esse cmdlet pode criar novos objetos de contato para uso com telefones de área comuns ou pode associar objetos de contato existentes a um novo telefone comum de área. Para modificar as propriedades dos objetos de contato associados a telefones de área comuns, use o cmdlet **set-CsCommonAreaPhone** . Os parâmetros opcionais para **set-CsCommonAreaPhone** permitem que você altere itens, como o nome de exibição do Active Directory do contato ou o URI (Uniform Resource Identifier) da linha associado ao telefone e habilite e desabilite a conta para uso com o Lync Server. Para obter detalhes sobre todas as modificações disponíveis, consulte a seção parâmetros em [set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Para obter detalhes sobre os parâmetros **New-CsCommonAreaPhone** , consulte [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

Você pode executar esses dois cmdlets a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Criando um objeto de contato de telefone de área comum

  - Para criar um novo objeto de contato de telefone de área comum, use o cmdlet **New-CsCommonAreaPhone** . No mínimo, você deve fornecer as seguintes informações ao criar um objeto de contato:
    
      - **LineUri**: o número de telefone atribuído ao telefone comum da área. Observe que você deve usar o formato E. 164 ao especificar o número de telefone.
    
      - **RegistrarPool**: o nome de domínio totalmente qualificado (FQDN) do pool de registradores que hospedará o objeto de contato.
    
      - **Ou**: nome diferenciado do contêiner do Active Directory em que o objeto de contato será criado.
    
    Também recomendamos que você forneça um nome de exibição dos serviços de domínio Active Directory. Caso contrário, será necessário usar um GUID para especificar a identidade do telefone. Por exemplo:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Modificando um objeto de contato de telefone de área comum

  - Para modificar as propriedades de um telefone de área comum existente, objeto de contato use o cmdlet **set-CsCommonAreaPhone** . Por exemplo, esse comando configura o endereço SIP para o telefone de área comum com o lobby DisplayName:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Para obter detalhes, consulte os tópicos da ajuda para o cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) e o cmdlet [set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

