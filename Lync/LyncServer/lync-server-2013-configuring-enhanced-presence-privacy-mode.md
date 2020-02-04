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
ms.openlocfilehash: 3cc68ad4e3200a268a2a6ea901167f211942c015
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Configurando o modo de privacidade de presença avançada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-08_

Com o modo de privacidade de presença avançada, os usuários podem restringir as informações de presença para que fiquem visíveis somente para os contatos listados na lista de contatos do Lync 2013. Os cmdlets **New-CsPrivacyConfiguration** e **set-CsPrivacyConfiguration** têm um parâmetro EnablePrivacyMode controla essa opção. Quando EnablePrivacyMode está definido como true, a opção de restringir as informações de presença aos contatos torna-se disponível nas opções de status do Lync 2013. Quando EnablePrivacyMode está definido como false, os usuários podem escolher para sempre permitir que todos vejam suas informações de presença ou para aderir a quaisquer alterações futuras feitas pelo administrador no modo de privacidade.

<div>


> [!IMPORTANT]  
> As configurações de privacidade do Lync 2013 e Lync 2010 não são respeitadas pelas versões anteriores (Microsoft Office Communicator 2007 R2 ou Microsoft Office Communicator 2007). Se as versões anteriores do Office Communicator tiverem permissão para entrar, um status do usuário do Lync 2013, informações de contato ou imagem podem ser visualizados por alguém que não tenha sido autorizado a visualizá-lo. Além disso, as configurações de privacidade do usuário do Lync 2013 são redefinidas se entrarem em mais tarde com a versão anterior do Communicator.<BR>Por esses motivos, em um cenário de migração, antes de habilitar o modo de privacidade de presença avançada: 
> <UL>
> <LI>
> <P>Certifique-se de que todos os usuários tenham o Lync 2013 instalado.</P>
> <LI>
> <P>Defina uma regra de política de versão do cliente para impedir que versões anteriores do Communicator entrem em entrar.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Para habilitar o modo de privacidade de presença avançada

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o seguinte comando:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Esse comando habilita o modo de privacidade para todas as configurações de privacidade em uso no momento na organização. Para obter mais informações sobre como as configurações de política do modo de privacidade de presença avançada do Lync Server gerencia a presença de contatos para o cliente do Lync 2013, consulte o artigo Microsoft Knowledge base [habilitar o modo de privacidade de presença avançada do Lync Server atualiza o status de presença de alguns contatos do Lync para "não disponível"](http://support.microsoft.com/kb/3020057).

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

