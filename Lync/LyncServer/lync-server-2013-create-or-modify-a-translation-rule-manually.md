---
title: 'Lync Server 2013: criar ou modificar uma regra de conversão manualmente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8225d5be1582add6a7dfd1a025b53da7c9b403b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Criar ou modificar uma regra de conversão manualmente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-06_

Siga estas etapas para definir uma regra de conversão desenvolvendo uma expressão regular para o padrão de correspondência e a regra de conversão. Como alternativa, você pode inserir um conjunto de valores na ferramenta **criar uma regra de conversão** e habilitar o painel de controle do Lync Server para gerar o padrão correspondente e a regra de conversão para você. Para obter detalhes, consulte [criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>Como definir uma regra de conversão manualmente

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Para começar a definir uma regra de conversão, siga as etapas em [configurar um tronco com bypass de mídia no Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) até a etapa 10 ou [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) até a etapa 9.

4.  No campo **Nome**, na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreva o padrão de número sendo convertido.

5.  (Opcional) No campo **Descrição**, digite a descrição da regra de conversção, por exemplo **Discagem internacional de longa distância dos EUA**.

6.  Clique em **Editar** na parte inferior da seção **Criar uma Regra de Conversão**.

7.  Insira no campo**Digite uma Expressão Regular** o seguinte:
    
      - No campo **Corresponder a este padrão**, especifique o padrão que será usado para corresponder os números a serem convertidos.
    
      - No campo **Regra de conversão**, especifique o padrão para o formato dos números convertidos.
    
    Por exemplo, se você inserir ** ^ \\+ (\\d{9}\\d +) $** em **corresponder este padrão** e **011 $1** em **regra de conversão**, a regra converterá + 441235551010 para 011441235551010.

8.  Clique em **OK** para salvar a regra de tradução.

9.  Clique em **OK** para salvar a configuração de tronco.

10. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
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

