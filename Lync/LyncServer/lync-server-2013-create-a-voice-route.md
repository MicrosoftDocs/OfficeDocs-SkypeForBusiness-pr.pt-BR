---
title: 'Lync Server 2013: criar uma rota de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4c6a9492cbbecafff95a1f6e626087e79f62d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>Criar uma rota de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O procedimento a seguir explica como criar uma nova rota de voz usando o painel de controle do Lync Server 2013. Para editar uma rota existente, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md) para obter o procedimento.

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Para criar uma rota de voz usando o painel de controle do Lync Server

1.  Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz**.

4.  Clique em **Rota**.

5.  Clique em **Novo** para exibir a caixa de diálogo **Nova Rota de Voz**.

6.  No campo **Nome**, digite o nome descritivo da rota de voz.

7.  (Opcional) Em **Descrição**, digite outras informações descritivas para a rota de voz.

8.  Para especificar os padrões que você deseja acomodar com essa rota, é possível usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou escrever manualmente a expressão regular.
    
      - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
        
          - **Dígitos iniciais para números que você deseja permitir:** Insira valores de prefixo que essa rota deve acomodar (incluindo o + + se necessário). Por exemplo, digite **+425** e clique em **Adicionar**. Repita este procedimento para cada valor de prefixo que deseja incluir na rota.
        
          - **Exceções:** Se você quiser especificar uma ou mais exceções para um valor de prefixo, realce o prefixo e clique em **exceções**. Digite um ou mais valores para os padrões de correspondência que você *não* deseja acomodar com essa rota. Por exemplo, para excluir números que começam com +425237 da rota, digite um valor de **+425237** no campo **Exceções** e clique em **OK**.
    
      - Para definir manualmente um padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada. Para obter detalhes sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)em.

9.  Selecione **Suprimir ID de chamadas** se não quiser que o ID do telefone que está fazendo a chamada apareça no destinatário da chamada. Se você selecionar essa opção, especifique um **ID de chamadas alternativo** que aparecerá no display de ID da chamada do destinatário.

10. Para associar um ou mais troncos à rota de voz, clique em **Adicionar** e selecione um tronco SIP ou gateway na lista.
    
    <div>
    

    > [!NOTE]  
    > Se sua implantação inclui qualquer servidor de mediação do Microsoft Office Communications Server 2007 R2, ele também estará disponível na lista.

    
    </div>

11. Para associar um ou mais usos de PSTN (rede telefônica pública comutada) com a rota de voz, clique em **selecionar** e escolha um registro na lista de registros de uso PSTN definidos para a implantação do Enterprise Voice.
    
    <div>
    

    > [!NOTE]  
    > Para exibir as propriedades de cada um dos registros de uso PSTN disponíveis, consulte <A href="lync-server-2013-view-pstn-usage-records.md">exibir registros de uso PSTN no Lync Server 2013</A>.<BR>Para criar ou editar registros de uso PSTN, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A>.

    
    </div>

12. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!NOTE]  
    > Em contraste à política de voz, onde a ordem no qual os registros de uso PSTN estão listados é importante, a ordem na qual os registros de uso PSTN estão listados na rota de voz é insignificante. No entanto, recomendamos organizar a lista por frequência de uso. Por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (O Lync Server percorre a lista de cima para baixo.)

    
    </div>

13. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
    <div>
    

    > [!NOTE]  
    > Você pode salvar uma rota de voz que ainda não passou no teste e, em seguida, reconfigurá-la mais tarde. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

14. Clique em **OK** para salvar a rota de voz.

<div>


> [!IMPORTANT]  
> Sempre que você criar uma rota de voz, deverá executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração da configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Exibir registros de uso de PSTN no Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

