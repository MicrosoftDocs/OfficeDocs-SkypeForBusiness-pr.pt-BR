---
title: 'Lync Server 2013: Configurando o modo de privacidade de presença avançada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32c8622e2c32af698d599b4ed541945b4d1de0a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Configurando o modo de privacidade de presença avançada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-08_

Com o modo de privacidade de presença avançada, os usuários podem restringir suas informações de presença para que fiquem visíveis somente para os contatos listados na lista de contatos do Lync 2013. Os cmdlets **New-CsPrivacyConfiguration** e **set-CsPrivacyConfiguration** têm um parâmetro EnablePrivacyMode controla essa opção. Quando EnablePrivacyMode é definido como true, a opção para restringir as informações de presença aos contatos fica disponível nas opções de status do Lync 2013. Quando EnablePrivacyMode está definido como False, os usuários podem optar por sempre permitir que qualquer pessoa veja as informações de presença ou aderir a qualquer mudança futura que o administrador faça no modo de privacidade.

<div>


> [!IMPORTANT]  
> As configurações de privacidade do Lync 2013 e Lync 2010 não são respeitadas por versões anteriores (Microsoft Office Communicator 2007 R2 ou Microsoft Office Communicator 2007). Se as versões anteriores do Office Communicator têm permissão para entrar, o status de um usuário do Lync 2013, as informações de contato ou a imagem podem ser vistos por alguém que não tenha sido autorizado a exibi-la. Além disso, as configurações de privacidade de um usuário do Lync 2013 são redefinidas se ele entrar mais tarde com a versão anterior do Communicator.<BR>Por esses motivos, em um cenário de migração, antes de habilitar o modo de privacidade de presença avançada: 
> <UL>
> <LI>
> <P>Certifique-se de que todos os usuários tenham o Lync 2013 instalado.</P>
> <LI>
> <P>Defina uma regra de política de versão do cliente para impedir que as versões anteriores do Communicator faça logon.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Para habilitar o modo de privacidade de presença avançada

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o seguinte comando:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Esse comando habilita o modo de privacidade para todas as definições de configuração da privacidade em uso na organização. Para obter mais informações sobre como as configurações de política do modo de privacidade de presença avançada do Lync Server gerenciam a presença de contato para o cliente Lync 2013, consulte o artigo da Microsoft KB [habilitando o modo de privacidade de presença avançada do Lync Server atualiza o status de presença de alguns contatos do Lync para "não disponível"](https://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

