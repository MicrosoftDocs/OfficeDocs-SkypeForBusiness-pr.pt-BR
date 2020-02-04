---
title: 'Lync Server 2013: Criar ou modificar uma regra de normalização manualmente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Criar ou modificar uma regra de normalização manualmente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-22_

Conclua as etapas a seguir se desejar criar ou modificar uma regra de normalização manualmente. Se você quiser criar ou modificar uma regra de normalização usando criar uma regra de normalização no painel de controle do Lync Server, consulte [criar ou modificar uma regra de normalização usando a regra criar uma normalização no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

<div>

## <a name="to-define-a-normalization-rule-manually"></a>Para definir uma regra de normalização manualmente

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Adicionais Siga as etapas em [criar um plano de discagem no Lync server 2013](lync-server-2013-create-a-dial-plan.md) ou [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  Em **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Nome** (por exemplo, o nome da regra de normalização **5DigitExtension**).

5.  (Opcional) No campo **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Traduzir extensões de 5 dígitos").

6.  Em **Compilar uma regra de normalização**, clique em **Editar**.

7.  Digite o seguinte em **Digitar uma expressão regular**:
    
      - Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.
    
      - Em **Regra de conversão**, especifique um padrão para o formato dos números de telefone E.164 convertidos.
    
    Por exemplo, se você inserir **^ (\\d{7}) $** em **coincidir este padrão** e **+ 1425 $1** na **regra de tradução**, a regra normalizará 5550100 para + 14255550100.

8.  (Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.

9.  (Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.
    
    <div>
    

    > [!NOTE]  
    > É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

10. Clique em **OK** para salvar a regra de normalização.

11. Clique em **OK** para salvar o plano de discagem.

12. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar ou alterar uma regra de normalização, você deve executar o comando <STRONG>Confirmar todos</STRONG> para publicar a alteração na configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar uma regra de normalização usando criar uma regra de normalização no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

