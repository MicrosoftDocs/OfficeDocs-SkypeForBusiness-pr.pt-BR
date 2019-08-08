---
title: Criar ou modificar um plano de discagem no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Resumo: saiba como criar ou modificar um plano de discagem usando o painel de controle do Skype for Business Server.'
ms.openlocfilehash: 456bd4c46b371da260340fab4e2b7152d14f7924
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240502"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Criar ou modificar um plano de discagem no Skype for Business Server

**Resumo:** Saiba como criar ou modificar um plano de discagem usando o painel de controle do Skype for Business Server.

### <a name="to-create-a-dial-plan"></a>Para criar um plano de discagem

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em  **Plano de Discagem**.

3. Na página **Plano de Discagem**, clique em  **Novo** e selecione um escopo para o plano de discagem:

   - **Plano de discagem do Site** se aplica a todo um site, exceto quaisquer usuários ou grupos que recebem um plano de discagem de usuário. Se você selecionar **site** para o escopo de um plano de discagem, deverá escolher o site na caixa de diálogo **selecionar um site** . Se já houver um plano de discagem para um site, o site não aparecerá na caixa de diálogo **Selecionar um Site**.

   - **Plano de discagem do pool** pode se aplicar a um gateway de PSTN (Rede Telefônica Pública Comutada) ou um registrador. Se você selecionar **pool** para o escopo de um plano de discagem, escolha o provedor ou o registrador de PSTN na caixa de diálogo **selecionar um serviço** . Se um plano de discagem já tiver sido criado para um serviço (gateway PSTN ou registrador), o serviço não aparecerá na lista.

   - **Plano de discagem do usuário** pode ser aplicado a usuários ou grupos especificados.

     > [!NOTE]
     > Depois de selecionar o escopo do plano de discagem, não é possível alterá-lo.

4. Se você estiver criando um plano de discagem do usuário, insira um nome descritivo no campo  **Nome** na caixa de diálogo **Novo Plano de Discagem**. Após o nome ser salvo, não será possível alterá-lo.

    > [!NOTE]
    > Para planos de discagem de site, o campo **nome** é preenchido previamente com o nome do site e não pode ser alterado. > para planos de discagem de pool, o campo **Name** é preenchido previamente com o nome do registrador ou o gateway PSTN e não pode ser alterado.

5. O campo  **Nome simples** é pré-preenchido com o mesmo nome que aparece no campo  **Nome**. Como opção, é possível editar esse campo para especificar um nome mais descritivo que reflete o site, o serviço ou o usuário ao qual o plano de discagem se aplica.

   > [!IMPORTANT]
   > O **nome simples** deve ser exclusivo entre todos os planos de discagem na sua implantação. Ele não pode exceder os caracteres Unicode do 256, sendo que cada um deles pode ser um caractere numérico ou alfabético, um hífen (-), um ponto (.) ou um sublinhado (_). **não há suporte para** caracteres de > incluir espaços<http://www.ietf.org/rfc/rfc3966.txt>e caracteres reservados conforme definidos em RFC 3966 (). Os caracteres reservados que **não têm suporte** no **nome simples** incluem o seguinte: > ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

6. (Opcional) No campo **Descrição**, você pode digitar informações descritivas adicionais sobre o plano de discagem.

7. (Opcional) Se você quiser usar esse plano de discagem como uma região para números de acesso de discagem, especifique uma **Região de conferência de discagem**. Se você não quiser usar esse plano de discagem para números de acesso de discagem, deixe esse campo vazio.

    > [!NOTE]
    > As regiões de conferência d discagem são necessárias para associar números de acesso de conferência de discagem a um ou mais planos de discagem.

8. (Opcional) No campo **Prefixo de acesso externo**, especifique um valor somente se os usuários precisarem discar um ou mais dígitos iniciais adicionais (por exemplo, 9) para obter uma linha externa. É possível digitar um valor de prefixo de até quatro caracteres (#, * e 0 a 9).

    > [!NOTE]
    > Se você especificar um prefixo de acesso externo, não será necessário criar uma nova regra de normalização para acomodar o prefixo.

9. Associe e configure as regras de normalização para o plano de discagem da seguinte maneira:

    - Para escolher uma ou mais regras de uma lista de todas as regras de normalização disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar as Regras de Normalização**, realce as regras que você deseja associar ao plano de discagem e clique em **OK**.

   - Para definir uma nova regra de normalização e associá-la ao plano de discagem, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [criar ou modificar uma regra de normalização no Skype for Business](normalization-rules.md).

   - Para editar uma regra de normalização que já está associada ao plano de discagem, realce o nome da regra e clique em **Mostrar detalhes**.

   - Para copiar uma regra de normalização existente a fim de usá-la como um ponto de partida para a definição de uma nova regra, realce o nome da regra e clique em **Copiar** e clique em **Colar**.

   - Para remover uma regra de normalização do plano de discagem, realce o nome da regra e clique em **Remover**.

     > [!NOTE]
     > Cada plano de discagem deve ter no mínimo uma regra de normalização associada. Para obter informações sobre como determinar todas as regras de normalização que um plano de discagem requer, consulte [planejar o roteamento de voz de saída no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) na documentação de planejamento.

10. Verifique se as regras de normalização do plano de discagem estão organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.

    > [!IMPORTANT]
    > O Skype for Business Server percorre a lista de regras de normalização de cima para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um plano de discagem de modo que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas. > o padrão **manter toda** a regra de normalização ^{11}(\d) $ corresponde a qualquer número de 11 dígitos. Por exemplo, se você adicionar uma regra de normalização que corresponda a números de 11 dígitos que comecem com o 1425, certifique-se de que a opção **manter tudo** esteja classificada{7}abaixo da regra mais restritiva (1425 \ d) $.

11. (Opcional) Insira um número para testar o plano de discagem e, em seguida, clique em  **Ir**. Os resultados do teste são exibidos em  **Insira um número de teste**.

12. Clique em **OK**.

13. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que você criar um plano de discagem, será necessário executar o comando **Confirmar tudo** para publicar a alteração na configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.

### <a name="to-modify-a-dial-plan"></a>Para modificar um plano de discagem

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em  **Plano de Discagem**.

4. Na página **Plano de Discagem**, dê um duplo clique no nome de um plano de discagem.

    > [!NOTE]
    > O escopo e o nome do plano de discagem foram definidos quando o plano de discagem foi criado. Eles não podem ser alterados.

5. (Opcional) Em **Editar Plano de Discagem**, edite o campo **Nome simples**, que é pré-preenchido com o mesmo nome que aparece no campo  **Nome** para especificar um nome mais descritivo que reflita o site, serviço ou usuário para o qual o plano de discagem se aplica.

    > [!IMPORTANT]
    > O **nome simples** deve ser exclusivo entre todos os planos de discagem na implantação do Lync Server 2013. Ele não pode exceder os caracteres Unicode do 256, sendo que cada um deles pode ser um caractere numérico ou alfabético, um hífen (-), um ponto (.), um sinal de adição (+) ou um sublinhado (_). > espaços não são permitidos no campo **nome simples** .

6. (Opcional) No campo **Descrição**, digite informações descritivas sobre o plano de discagem.

7. (Opcional) Se você quiser usar esse plano de discagem como uma região para números de acesso de discagem, especifique uma **Região de conferência de discagem**. Se você não quiser usar esse plano de discagem para números de acesso de discagem, deixe esse campo vazio.

    > [!NOTE]
    > As regiões de conferência d discagem são necessárias para associar números de acesso de conferência discada a um ou mais planos de discagem.

8. (Opcional) No campo **Prefixo de acesso externo**, especifique um valor somente se usuários precisarem discar um ou mais dígitos primeiro para obter uma linha externa (por exemplo, 9). Você pode digitar um valor de prefixo de até quatro caracteres (isto é, #, * e 0-9).

    > [!NOTE]
    > Se você especificar um prefixo de acesso externo, não será necessário criar uma nova regra de normalização para acomodar o prefixo.

9. Associe e configure regras de normalização para o plano de discagem:

   - Para escolher uma ou mais regras de uma lista de todas as regras de normalização disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Na caixa de diálogo **Selecionar Regras de Normalização**, destaque as regras que deseja associar ao plano de discagem e clique em **OK**.

   - Para definir uma nova regra de normalização e associá-la ao plano de discagem, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [criar ou modificar uma regra de normalização no Skype for Business](normalization-rules.md).

   - Para editar uma regra de normalização que já está associada ao plano de discagem, realce o nome da regra e clique em **Mostrar detalhes**.

   - Para copiar uma regra de normalização existente a fim de usá-la como um ponto de partida para a definição de uma nova regra, realce o nome da regra e clique em **Copiar** e clique em **Colar**.

   - Para remover uma regra de normalização do plano de discagem, realce o nome da regra e clique em **Remover**.

     > [!NOTE]
     > Cada plano de discagem deve ter no mínimo uma regra de normalização associada. Para obter detalhes sobre como determinar todas as regras de normalização que um plano de discagem requer, consulte [planejar o roteamento de voz de saída no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) na documentação de planejamento.

10. Verifique se as regras de normalização do plano de discagem estão organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.

    > [!IMPORTANT]
    > O Skype for Business Server percorre a lista de regras de normalização de cima para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um plano de discagem de modo que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas. > o padrão **manter toda** a regra de normalização ^{11}(\d) $ corresponde a qualquer número de 11 dígitos. Se, por exemplo, você adicionar uma regra de normalização que corresponda a números de 11 dígitos que comecem com o 1425, certifique-se de que a opção **manter tudo** esteja classificada{7}abaixo da regra ^ (1425 \ d) mais restritiva.

11. (Opcional) Insira um número para testar o plano de discagem e, em seguida, clique em  **Ir**. Os resultados do teste são exibidos em  **Insira um número de teste**.

    > [!NOTE]
    > É possível salvar um plano de discagem que não passou ainda no teste e reconfigurá-lo mais tarde. Para obter detalhes, consulte [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

12. Clique em **OK**.

13. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou modificar um plano de discagem, você deve executar o comando  **Confirmar tudo** para publicar as alterações de configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.

## <a name="see-also"></a>Confira também

[Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md)

