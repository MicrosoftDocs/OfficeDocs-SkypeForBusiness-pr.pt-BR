---
title: Criar ou modificar uma regra de tradução usando a ferramenta criar regra de tradução
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06f498af25dfd851bd2950ce08d5c66179b95ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Criar ou modificar uma regra de tradução usando a ferramenta construir uma regra de tradução no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

Siga estas etapas se quiser definir uma regra de tradução inserindo um conjunto de valores na ferramenta **criar regra de tradução** e habilitando o painel de controle do Lync Server para gerar o padrão correspondente e a regra de tradução para você. Se preferir, é possível gravar uma expressão regular manualmente para definir o padrão de correspondência e a regra de conversão. Para obter detalhes, consulte [criar ou modificar uma regra de tradução manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para começar a definir uma regra de tradução, siga as etapas em [configurar um tronco com bypass de mídia no Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) até a etapa 10 ou [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) até a etapa 9.

4.  Em  **Nome** na página  **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.

5.  (Opcional) Em  **Descrição**, digite uma descrição da regra de conversão, por exemplo  **US International long-distance dialing**.

6.  Na seção  **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:
    
      - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, insira **+** nesse campo para corresponder os números no formato E. 164 (que começa com +).
    
      - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite  **11** e selecione  **At least** na lista suspensa para fazer a correspondência de números com no mínimo 11 dígitos de comprimento.
    
      - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, insira **1** para distribuir o **+** do início do número.
    
      - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite  **011** se quiser que 011 seja anexado aos números convertidos quando a regra for aplicada.
    
    Os valores inseridos nesses campos são refletidos nos campos  **Padrão a ser correspondido** e  **Regra de conversão**. Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo  **Padrão a ser correspondido** será:
    
    **^\\+ (\\p{9}\\+) $**
    
    O campo  **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:
    
      - Um valor (por exemplo, **$1**) que representa o número de dígitos no padrão de correspondência
    
      - Adicionais Um valor que você pode preceder inserindo-o no campo **dígitos para adicionar**
    
    Usando os valores de exemplo anteriores, **011 $1** é exibido no campo **regra de tradução** .
    
    Quando essa regra de tradução é aplicada, + 441235551010 se torna 011441235551010.

7.  Clique em **OK** para salvar a regra de tradução.

8.  Clique em **OK** para salvar a configuração do tronco.

9.  Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]
    > Sempre que você cria ou modifica uma regra de tradução, deve executar o comando <STRONG>Commit All</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar uma regra de tradução manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
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

