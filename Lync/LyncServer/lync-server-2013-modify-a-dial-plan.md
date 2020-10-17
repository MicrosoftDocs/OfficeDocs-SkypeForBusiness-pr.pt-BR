---
title: 'Lync Server 2013: modificar um plano de discagem'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db84f9b353450419a8cc8029e4a24d01f0df76b5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534408"
---
# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Modificar um plano de discagem no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Para modificar um plano de discagem existente, execute as etapas do procedimento a seguir. Se você quiser criar um novo plano de discagem, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-modify-a-dial-plan"></a>Para modificar um plano de discagem

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Plano de Discagem**.

4.  Na página **Plano de Discagem**, dê um duplo clique no nome de um plano de discagem.
    
    <div>
    

    > [!NOTE]  
    > O nome e o escopo do plano de discagem foram definidos quando o plano de discagem foi criado. Eles não podem ser alterados.

    
    </div>

5.  Opcion Em **Editar plano de discagem**, edite o campo **nome simples** , que é preenchido previamente com o mesmo nome que aparece no campo **nome** para especificar um nome mais descritivo que reflita o site, o serviço ou o usuário ao qual o plano de discagem se aplica.
    
    <div>
    

    > [!IMPORTANT]  
    > O <STRONG>nome simples</STRONG> deve ser exclusivo entre todos os planos de discagem na implantação do Lync Server 2013. Ele não pode exceder 256 caracteres Unicode, e cada um deles pode ser um caractere alfabético ou numérico, um hífen (-), um ponto (.), um sinal de adição (+) ou um sublinhado (_).<BR>Espaços não são permitidos no campo <STRONG>nome simples</STRONG> .

    
    </div>

6.  Opcion No campo **Descrição** , digite informações descritivas sobre o plano de discagem.

7.  (Opcional) Se você quiser usar esse plano de discagem como uma região para números de acesso de discagem, especifique uma **Região de conferência de discagem**. Se você não quiser usar esse plano de discagem para números de acesso de discagem, deixe esse campo vazio.
    
    <div>
    

    > [!NOTE]  
    > As regiões de conferência d discagem são necessárias para associar números de acesso de conferência de discagem a um ou mais planos de discagem.

    
    </div>

8.  Opcion No campo **prefixo de acesso externo** , especifique um valor somente se os usuários precisarem discar um ou mais dígitos iniciais adicionais para obter uma linha externa (por exemplo, 9). Você pode digitar um valor de prefixo de até quatro caracteres (ou seja,, \# \* e 0-9).
    
    <div>
    

    > [!NOTE]  
    > Se você especificar um prefixo de acesso externo, não será necessário criar uma nova regra de normalização para acomodar o prefixo.

    
    </div>

9.  Associar e configurar regras de normalização para o plano de discagem:
    
      - Para escolher uma ou mais regras de uma lista de todas as regras de normalização disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Na caixa de diálogo **selecionar regras de normalização** , realce as regras que você deseja associar ao plano de discagem e clique em **OK**.
    
      - Para definir uma nova regra de normalização e associá-la ao plano de discagem, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para editar uma regra de normalização que já está associada ao plano de discagem, realce o nome da regra e clique em **Mostrar detalhes**. Para obter detalhes sobre a edição da regra, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para copiar uma regra de normalização existente a fim de usá-la como um ponto de partida para a definição de uma nova regra, realce o nome da regra e clique em **Copiar** e clique em **Colar**. Para obter detalhes sobre como editar a cópia, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para remover uma regra de normalização do plano de discagem, realce o nome da regra e clique em **Remover**.
    
    <div>
    

    > [!NOTE]  
    > Cada plano de discagem precisa ter pelo menos uma regra de normalização associada. Para obter detalhes sobre como determinar todas as regras de normalização exigidas por um plano de discagem, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial Plans and Normalization Rules in Lync Server 2013</A> na documentação de planejamento.

    
    </div>

10. Verifique se as regras de normalização do plano de discagem são organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!IMPORTANT]  
    > O Lync Server percorre a lista de regras de normalização de cima para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um plano de discagem de modo que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas.<BR>O padrão <STRONG>manter todas as</STRONG> regras de normalização <STRONG>^ (\d {11} ) $</STRONG> corresponde a qualquer número de 11 dígitos. Se, por exemplo, você adicionar uma regra de normalização que corresponda a números de 11 dígitos que começam com 1425, certifique-se de que <STRONG>manter todos</STRONG> esteja classificado abaixo da regra <STRONG>^ (1425 \ d {7} ) $</STRONG> mais restritiva.

    
    </div>

11. (Opcional) Insira um número para testar o plano de discagem e, em seguida, clique em   **Ir **. Os resultados do teste são exibidos em   **Insira um número de teste **.
    
    <div>
    

    > [!NOTE]  
    > É possível salvar um plano de discagem que não passou ainda no teste e reconfigurá-lo mais tarde. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

12. Clique em **OK**.

13. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar ou modificar um plano de discagem, você deve executar o comando <STRONG>confirmar tudo</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

