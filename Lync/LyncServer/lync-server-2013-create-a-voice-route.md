---
title: 'Lync Server 2013: criar uma rota de voz'
description: 'Lync Server 2013: criar uma rota de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a9becac8b35967d7b7ff05014bd6b6600f62a06
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562427"
---
# <a name="create-a-voice-route-in-lync-server-2013"></a>Criar uma rota de voz no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O procedimento a seguir explica como criar uma nova rota de voz usando o painel de controle do Lync Server 2013. Para editar uma rota existente, confira [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md) para o procedimento.

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Para criar uma rota de voz usando o painel de controle do Lync Server

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz**.

4.  Clique em **Rota**.

5.  Clique em **Novo** para exibir a caixa de diálogo **Nova Rota de Voz**.

6.  Em **nome**, digite um nome descritivo para a rota de voz.

7.  Opcion Em **Descrição**, digite informações descritivas adicionais para a rota de voz.

8.  Para especificar os padrões que você deseja que essa rota acomode, você pode usar a ferramenta **criar um padrão de correspondência** para gerar uma expressão regular ou gravar a expressão regular manualmente.
    
      - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
        
          - **Dígitos iniciais para números que você deseja permitir:** Insira valores de prefixo que essa rota deve acomodar (incluindo a entrelinha +, se necessário). Por exemplo, digite **+ 425**e, em seguida, clique em **Adicionar**. Repita isso para cada valor de prefixo que você deseja incluir na rota.
        
          - **Exceções:** Se você quiser especificar uma ou mais exceções para um valor de prefixo, realce o prefixo e clique em **exceções**. Digite um ou mais valores para os padrões de correspondência que você *não* deseja acomodar com essa rota. Por exemplo, para excluir números que começam com + 425237 da rota, insira um valor de **+ 425237** no campo **exceções** e clique em **OK**.
    
      - Para definir manualmente o padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada. Para obter detalhes sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" em [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

9.  Selecione **Suprimir ID de chamadas** se não quiser que o ID do telefone que está fazendo a chamada apareça no destinatário da chamada. Se você selecionar essa opção, especifique um **ID de chamadas alternativo** que aparecerá no display de ID da chamada do destinatário.

10. Para associar um ou mais troncos à rota de voz, clique em **Adicionar** e selecione um tronco na lista.
    
    <div>
    

    > [!NOTE]  
    > Se sua implantação incluir quaisquer servidores de mediação do Microsoft Office Communications Server 2007 R2, eles também estarão disponíveis na lista.

    
    </div>

11. Para associar um ou mais usos de PSTN (rede telefônica pública comutada) à rota de voz, clique em **selecionar** e escolha um registro na lista de registros de uso de PSTN que foram definidos para sua implantação do Enterprise Voice.
    
    <div>
    

    > [!NOTE]  
    > Para exibir as propriedades de cada um dos registros de uso de PSTN disponíveis, consulte <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN Usage Records in Lync Server 2013</A>.<BR>Para criar ou editar registros de uso de PSTN, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso de PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A>.

    
    </div>

12. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!NOTE]  
    > Ao contrário de uma política de voz, onde a ordem na qual os registros de uso PSTN são listados é importante, a ordem na qual os registros de uso PSTN são listados na rota de voz é insignificante. No entanto, recomendamos que você organize a lista por frequência de uso. Por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (O Lync Server percorre a lista de cima para baixo.)

    
    </div>

13. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
    <div>
    

    > [!NOTE]  
    > É possível salvar uma rota de voz que não passou ainda no teste e reconfigurá-la mais tarde. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

14. Clique em **OK** para salvar a rota de voz.

<div>


> [!IMPORTANT]  
> Sempre que você cria uma rota de voz, deve executar o comando <STRONG>confirmar tudo</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Exibir registros de uso de PSTN no Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

