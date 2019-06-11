---
title: 'Lync Server 2013: criar um plano de discagem'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8734ce4503ef62eb0fc04aab376f2819d1fc8fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a>Criar um plano de discagem no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-24_

Para criar um novo plano de discagem, siga as etapas do procedimento a seguir. Se você quiser editar um plano de discagem, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-create-a-dial-plan"></a>Para criar um plano de discagem

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em  **Plano de Discagem**.

4.  Na página **Plano de Discagem**, clique em  **Novo** e selecione um escopo para o plano de discagem:
    
      - **Plano de discagem do Site** se aplica a todo um site, exceto quaisquer usuários ou grupos que recebem um plano de discagem de usuário. Se você selecionar **Site** para o escopo de um plano de discagem, deverá escolher o site na caixa de diálogo **Selecionar um Site**. Se já houver um plano de discagem para um site, o site não aparecerá na caixa de diálogo **Selecionar um Site**.
    
      - **Plano de discagem do pool** pode se aplicar a um gateway de PSTN (Rede Telefônica Pública Comutada) ou um registrador. Se você selecionar  **Pool** para o escopo de um plano de discagem, escolha o gateway PSTN ou registrador na caixa de diálogo  **Selecionar um Serviço**. Se um plano de discagem já tiver sido criado para um serviço (gateway PSTN ou registrador), o serviço não aparecerá na lista.
    
      - **Plano de discagem do usuário** pode ser aplicado a usuários ou grupos especificados.
    
    <div>
    

    > [!NOTE]  
    > Depois de selecionar o escopo do plano de discagem, não é possível alterá-lo.

    
    </div>

5.  Se você estiver criando um plano de discagem do usuário, insira um nome descritivo no campo  **Nome** na caixa de diálogo **Novo Plano de Discagem**. Após o nome ser salvo, não será possível alterá-lo.
    
    <div>
    

    > [!NOTE]  
    > Para planos de discagem do site, o campo  <STRONG>Nome</STRONG> é pré-preenchido com o nome do site e não pode ser alterado.<BR>Para planos de discagem do pool, o campo  <STRONG>Nome</STRONG> é pré-preenchido com o gateway PSTN ou o nome do registrador e não pode ser alterado.

    
    </div>

6.  O campo  **Nome simples** é pré-preenchido com o mesmo nome que aparece no campo  **Nome**. Como opção, é possível editar esse campo para especificar um nome mais descritivo que reflete o site, o serviço ou o usuário ao qual o plano de discagem se aplica.
    
    <div>
    

    > [!IMPORTANT]  
    > O <STRONG>nome simples</STRONG> deve ser exclusivo entre todos os planos de discagem na implantação do Lync Server. Ele não pode exceder os caracteres Unicode do 256, sendo que cada um deles pode ser um caractere numérico ou alfabético, um hífen (-), um ponto (.) ou um sublinhado (_).<BR>Os caracteres <STRONG>sem suporte</STRONG> incluem espaços e caracteres reservados, conforme definidos em RFChttp://www.ietf.org/rfc/rfc3966.txt)3966 (. Caracteres reservados <STRONG>não suportados</STRONG> no <STRONG>Nome Simples</STRONG> incluem o seguinte:<BR>";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.  (Opcional) No campo **Descrição**, você pode digitar informações descritivas adicionais sobre o plano de discagem.

8.  (Opcional) Se você quiser usar esse plano de discagem como uma região para números de acesso de discagem, especifique uma **Região de conferência de discagem**. Se você não quiser usar esse plano de discagem para números de acesso de discagem, deixe esse campo vazio.
    
    <div>
    

    > [!NOTE]  
    > As regiões de conferência d discagem são necessárias para associar números de acesso de conferência de discagem a um ou mais planos de discagem.

    
    </div>

9.  (Opcional) No campo **Prefixo de acesso externo**, especifique um valor somente se os usuários precisarem discar um ou mais dígitos iniciais adicionais (por exemplo, 9) para obter uma linha externa. Você pode digitar um valor de prefixo de até quatro caracteres (\#, \*e 0-9).
    
    <div>
    

    > [!NOTE]  
    > Se você especificar um prefixo de acesso externo, não será necessário criar uma nova regra de normalização para acomodar o prefixo.

    
    </div>

10. Associe e configure as regras de normalização para o plano de discagem da seguinte maneira:
    
      - Para escolher uma ou mais regras de uma lista de todas as regras de normalização disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar as Regras de Normalização**, realce as regras que você deseja associar ao plano de discagem e clique em **OK**.
    
      - Para definir uma nova regra de normalização e associá-la ao plano de discagem, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para editar uma regra de normalização que já está associada ao plano de discagem, realce o nome da regra e clique em **Mostrar detalhes**. Para obter detalhes sobre a edição da regra, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para copiar uma regra de normalização existente a fim de usá-la como um ponto de partida para a definição de uma nova regra, realce o nome da regra e clique em **Copiar** e clique em **Colar**. Para obter detalhes sobre como editar a cópia, consulte [definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md).
    
      - Para remover uma regra de normalização do plano de discagem, realce o nome da regra e clique em **Remover**.
    
    <div>
    

    > [!NOTE]  
    > Cada plano de discagem deve ter no mínimo uma regra de normalização associada. Para obter informações sobre como determinar todas as regras de normalização que um plano de discagem requer, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planos de discagem e regras de normalização no Lync Server 2013</A> na documentação de planejamento.

    
    </div>

11. Verifique se as regras de normalização do plano de discagem estão organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!IMPORTANT]  
    > O Lync Server percorre a lista de regras de normalização da parte superior para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um plano de discagem de modo que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas.<BR>O padrão <STRONG>manter toda</STRONG> a regra de normalização <STRONG>^{11}(\d) $</STRONG> corresponde a qualquer número de 11 dígitos. Por exemplo, se você adicionar uma regra de normalização que corresponda a números de 11 dígitos que comecem com o 1425, certifique-se de que a opção <STRONG>manter tudo</STRONG> esteja classificada abaixo da regra mais restritiva <STRONG>(1425 \ d{7}) $</STRONG> .

    
    </div>

12. (Opcional) Insira um número para testar o plano de discagem e, em seguida, clique em  **Ir**. Os resultados do teste são exibidos em  **Insira um número de teste**.
    
    <div>
    

    > [!NOTE]  
    > É possível salvar um plano de discagem que não passou ainda no teste e reconfigurá-lo mais tarde. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

13. Clique em **OK**.

14. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que você criar um plano de discagem, será necessário executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração na configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Definindo regras de normalização no Lync Server 2013](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

