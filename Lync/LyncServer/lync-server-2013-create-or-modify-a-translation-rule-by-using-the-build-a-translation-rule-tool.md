---
title: Criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9641170534c4c4ad1ef4976d018699d01d6069a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

Siga estas etapas se você quiser definir uma regra de conversão inserindo um conjunto de valores na ferramenta **criar uma regra de conversão** e habilitando o painel de controle do Lync Server para gerar o padrão correspondente e a regra de conversão para você. Se preferir, é possível gravar uma expressão regular manualmente para definir o padrão de correspondência e a regra de conversão. Para obter detalhes, consulte [criar ou modificar uma regra de conversão manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para começar a definir uma regra de conversão, siga as etapas em [configurar um tronco com bypass de mídia no Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) até a etapa 10 ou [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) até a etapa 9.

4.  Em **Nome** na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.

5.  (Opcional) Em **Descrição**, digite uma descrição da regra de conversão, por exemplo **Discagem de longa distância internacional EUA**.

6.  Na seção **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:
    
      - **Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda. Por exemplo, insira **+** neste campo para corresponder os números no formato E. 164 (que começa com +).
    
      - **Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite **11** e selecione **No mínimo** na lista suspensa para fazer a correspondência de números com no mínimo 11 dígitos de comprimento.
    
      - **Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos. Por exemplo, insira **1** para retirar o **+** desde o início do número.
    
      - **Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite **011** se quiser que 011 seja anexado aos números convertidos quando a regra é aplicada.
    
    Os valores inseridos nesses campos são refletidos nos campos **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo **Padrão a ser correspondido** será:
    
    **^\\+ (\\d{9}\\d +) $**
    
    O campo **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:
    
      - Um valor (por exemplo, **$1**) que representa o número de dígitos no padrão correspondido
    
      - (Opcional) Um valor que pode ser anexado digitando no campo **Dígitos a adicionar**
    
    Usando os valores do exemplo anterior, **011$1** aparece no campo **Regra de conversão**.
    
    Quando essa regra de conversão é aplicada, +441235551010 se torna 011441235551010.

7.  Clique em **OK** para salvar a regra de tradução.

8.  Clique em **OK** para salvar a configuração de tronco.

9.  Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]
    > Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar uma regra de conversão manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

