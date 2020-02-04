---
title: Criar ou modificar uma regra de normalização usando criar uma regra de normalização
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 519d4d8ee00e0922d40155c541b0f869df095ab1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Criar ou modificar uma regra de normalização usando criar uma regra de normalização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Conclua as etapas a seguir se desejar criar ou modificar uma regra de normalização no painel de controle do Lync Server. Como alternativa, se você quiser criar ou modificar uma regra de normalização manualmente, consulte [criar ou modificar uma regra de normalização manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>Para definir uma regra usando criar uma regra de normalização

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Adicionais Siga as etapas em [criar um plano de discagem no Lync server 2013](lync-server-2013-create-a-dial-plan.md) até a etapa 11 ou [modifique um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) até a etapa 10.

4.  Em  **Nova Regra de Normalização** ou **Editar Regra de Normalização**, digite um nome que descreva o padrão numérico que está sendo normalizado em **Nome** (por exemplo, **5DigitExtension**).

5.  (Opcional) Em **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Converte extensões de cinco dígitos").

6.  Em **Compilar uma Regra de Normalização**, digite valores nos campos a seguir:
    
      - **Dígitos iniciais (**   opcional) especifique os dígitos à esquerda dos números discados para os quais você deseja que o padrão corresponda. Por exemplo, digite **425** se quiser que o padrão corresponda aos números discados que comecem com 425.
    
      - **Comprimento**   especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda exatamente a esse comprimento, corresponde a números discados com pelo menos esse comprimento ou coincide com números discados de qualquer comprimento.
    
      - **Dígitos a serem**   removidos (opcional) especifique o número de dígitos iniciais a serem removidos dos números discados que você deseja que o padrão corresponda.
    
      - **Dígitos para adicionar**   (opcional) especifique os dígitos a serem adicionados aos números discados para os quais você deseja que o padrão corresponda.
    
    Os valores inseridos nesses campos são refletidos em **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você deixar **Dígitos iniciais** vazio, digite **7** no campo **Tamanho** e selecione **Exatamente** e especifique **0** em **Dígitos a serem removidos**, a expressão regular resultante em **Padrão a ser correspondido** será:
    
    **^ (\\d{7}) $**

7.  Em **Regra de conversão**, especifique um padrão para o formato de números de telefone E.164 convertido da seguinte maneira:
    
      - Um valor que representa o número de dígitos especificado no padrão de correspondência. Por exemplo, se o padrão correspondente for **^ (\\d{7}) $** , **$1** na regra de tradução representará os números discados de 7 dígitos.
    
      - (Opcional) Digite um valor no campo **Dígitos a adicionar** para especificar os dígitos a serem anexados ao número convertido, (por exemplo **+1425**).
    
    Por exemplo, se **a correspondência de padrão** contiver **\\^{7}(d) $** como o padrão para números discados e **regra de tradução** contém **+ 1425 $1** como o padrão para os números de telefone e. 164, a regra normaliza 5550100 para + 14255550100.

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


[Criar ou modificar uma regra de normalização manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
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

