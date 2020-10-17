---
title: 'Lync Server 2013: modificar uma rota de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6e2a3f255a77d7773d24d654c5c207b59b887bc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515338"
---
# <a name="modify-a-voice-route-in-lync-server-2013"></a>Modificar uma rota de voz no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Este tópico explica como editar uma rota de voz. Para criar uma nova rota, confira [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).

<div>

## <a name="to-modify-a-voice-route"></a>Para modificar uma rota de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Rota**.

4.  Na página **Rota**, use um dos métodos a seguir par modificar uma rota de voz:
    
      - Clique no nome de uma rota de voz, clique em **Editar** e em **Exibir detalhes**.
    
      - Clique no nome de uma rota de voz, clique em **Editar**, **Copiar** e, em seguida, em **Colar**. Clique na nova cópia da rota de voz que você acabou de criar, clique em **Editar** e em **Exibir detalhes**.

5.  No campo **Nome** na página **Editar Rota de Voz**, digite um nome descritivo para a rota de voz.

6.  (Opcional) No campo **Descrição**, digite informações descritivas adicionais para a rota de voz.

7.  Para especificar os padrões que você deseja acomodar com essa rota, use a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou escrever manualmente a expressão regular.
    
      - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
        
          - **Dígitos iniciais para números que você deseja permitir:** Insira valores de prefixo que essa rota deve acomodar (incluindo a entrelinha +, se necessário). Por exemplo, digite **+425** e clique em **Adicionar**. Repita isso para cada valor de prefixo que você deseja incluir na rota.
        
          - **Exceções:** Se você quiser especificar uma ou mais exceções para um valor de prefixo, realce o prefixo e clique em **exceções**. Digite um ou mais valores para os padrões de correspondência que você *não* deseja acomodar com essa rota. Por exemplo, para excluir números que começam com + 425237 da rota, insira um valor de **+ 425237** no campo **exceções** e clique em **OK**.
    
      - Para definir manualmente o padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada. Para obter informações sobre como escrever expressões regulares, consulte "expressões regulares do .NET Framework" em [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

8.  Selecione **suprimir ID de chamadas** se você não quiser que a ID do telefone que está fazendo a chamada de saída apareça para o destinatário da chamada. Se você selecionar essa opção, especifique um **ID de chamadas alternativo** que aparecerá no display de ID da chamada do destinatário.

9.  Para associar um ou mais troncos PSTN (rede telefônica pública comutada) à rota de voz, clique em **Adicionar**e selecione um tronco na lista.
    
    <div>
    

    > [!NOTE]  
    > Se sua implantação incluir quaisquer servidores de mediação do Microsoft Office Communications Server 2007 R2, eles também estarão disponíveis na lista.

    
    </div>

10. Para associar um ou mais usos de PSTN à rota de voz, clique em **selecionar** e escolha um registro na lista de registros de uso de PSTN que foram definidos para sua implantação do Enterprise Voice.
    
    <div>
    

    > [!NOTE]  
    > Para exibir as propriedades de cada um dos registros de uso de PSTN disponíveis, consulte <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN Usage Records in Lync Server 2013</A>.<BR>Para criar ou editar registros de uso de PSTN, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso de PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A>.

    
    </div>

11. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!NOTE]  
    > Ao contrário de uma política de voz onde a ordem na qual os registros de uso PSTN são listados é importante, a ordem dos registros de uso de PSTN em uma rota de voz é insignificante. No entanto, recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (O Lync Server percorre a lista de cima para baixo.)

    
    </div>

12. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
    <div>
    

    > [!NOTE]  
    > É possível salvar uma rota de voz que não passou ainda no teste e reconfigurá-la mais tarde. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

13. Clique em **OK**.

14. Na página **Rota**, clique em **Confirmar** e em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar ou modificar uma rota de voz, você deve executar o comando <STRONG>confirmar tudo</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
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

