---
title: 'Lync Server 2013: criar ou modificar manualmente uma regra de tradução'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Criar ou modificar uma regra de tradução manualmente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-08-06_

Siga estas etapas se quiser definir uma regra de tradução escrevendo uma expressão regular para o padrão correspondente e regra de tradução. Você também pode inserir um conjunto de valores na ferramenta **construir uma regra de tradução** e habilitar o painel de controle do Lync Server para gerar o padrão correspondente e a regra de tradução para você. Para obter detalhes, consulte [criar ou modificar uma regra de tradução usando a ferramenta criar regra de tradução no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>Para definir uma regra de tradução manualmente

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para começar a definir uma regra de tradução, siga as etapas em [configurar um tronco com bypass de mídia no Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) até a etapa 10 ou [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) até a etapa 9.

4.  No campo **nome** da página **nova regra de tradução** ou **Editar regra de tradução** , digite um nome que descreva o padrão de número que está sendo traduzido.

5.  Adicionais Em **Descrição**, digite uma descrição da regra de tradução, por exemplo, para a discagem de **longa distância internacional dos EUA**.

6.  Clique em **Editar** na parte inferior da seção **construir uma regra de tradução** .

7.  Digite o seguinte em **Digitar uma expressão regular**:
    
      - Em **coincidir com esse padrão**, especifique o padrão que será usado para corresponder os números a serem traduzidos.
    
      - Em **regra de tradução**, especifique um padrão para o formato dos números traduzidos.
    
    Por exemplo, se você digitar ** ^ \\+ (\\d{9}\\+) $** em **Match this Pattern** e **011 $1** na **regra de tradução**, a regra irá traduzir + 441235551010 para 011441235551010.

8.  Clique em **OK** para salvar a regra de tradução.

9.  Clique em **OK** para salvar a configuração do tronco.

10. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que você cria ou modifica uma regra de tradução, deve executar o comando <STRONG>Commit All</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar uma regra de tradução usando a ferramenta construir uma regra de tradução no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

