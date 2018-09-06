---
title: Criar ou modificar um plano de discagem no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Resumo: Saiba como criar ou modificar um plano de discagem usando o Skype para painel de controle do servidor de negócios.'
ms.openlocfilehash: b14d03447ed533a9695e4573a2f6a87c7e72ad53
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23243758"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Criar ou modificar um plano de discagem no Skype para Business Server

**Resumo:** Saiba como criar ou modificar um plano de discagem usando o Skype para painel de controle do servidor de negócios.

### <a name="to-create-a-dial-plan"></a>Para criar um plano de discagem

1. Abra o Skype para painel de controle do servidor de negócios.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em  **Plano de Discagem**.

3. Na página **Plano de Discagem**, clique em  **Novo** e selecione um escopo para o plano de discagem:

   - **Plano de discagem do Site** se aplica a todo um site, exceto quaisquer usuários ou grupos que recebem um plano de discagem de usuário. Se você selecionar um **Site** para o escopo de um plano de discagem, você deve escolher o site da caixa de diálogo **Selecionar um Site** . Se já houver um plano de discagem para um site, o site não aparecerá na caixa de diálogo **Selecionar um Site**.

   - **Plano de discagem do pool** pode se aplicar a um gateway de PSTN (Rede Telefônica Pública Comutada) ou um registrador. Se você selecionar um **Pool** para o escopo de um plano de discagem, escolha o gateway PSTN ou registrador de caixa de diálogo **Selecionar um serviço** . Se um plano de discagem já tiver sido criado para um serviço (gateway PSTN ou registrador), o serviço não aparecerá na lista.

   - **Plano de discagem do usuário** pode ser aplicado a usuários ou grupos especificados.

    > [!NOTE]
    > Depois de selecionar o escopo do plano de discagem, não é possível alterá-lo.

4. Se você estiver criando um plano de discagem do usuário, insira um nome descritivo no campo  **Nome** na caixa de diálogo **Novo Plano de Discagem**. Após o nome ser salvo, não será possível alterá-lo.

    > [!NOTE]
    > Para planos de discagem do site, o campo **nome** é pré-preenchido com o nome do site e não pode ser alterado. > para planos de discagem do pool, o campo **nome** é pré-preenchido com o gateway PSTN ou o nome do registrador e não pode ser alterado.

5. O campo  **Nome simples** é pré-preenchido com o mesmo nome que aparece no campo  **Nome**. Como opção, é possível editar esse campo para especificar um nome mais descritivo que reflete o site, o serviço ou o usuário ao qual o plano de discagem se aplica.

    > [!IMPORTANT]
    > O **nome simples** deve ser exclusivo entre todos os planos de discagem em sua implantação. Ele não pode exceder 256 caracteres Unicode, cada um deles pode ser um caractere de caracteres alfabético ou numérico, um hífen (-), um ponto (.) ou um sublinhado (_). > caracteres **não suportados** incluem espaços e caracteres reservados como definido no RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt). Caracteres reservados que estão **não tem suporte** no **Nome simples** incluem o seguinte: > ";" "/" "?" ":" "@" "&amp;" "=" "+""$",""

6. (Opcional) No campo **Descrição**, você pode digitar informações descritivas adicionais sobre o plano de discagem.

7. (Opcional) Se você quiser usar esse plano de discagem como uma região para números de acesso de discagem, especifique uma **Região de conferência de discagem**. Se você não quiser usar esse plano de discagem para números de acesso de discagem, deixe esse campo vazio.

    > [!NOTE]
    > As regiões de conferência d discagem são necessárias para associar números de acesso de conferência de discagem a um ou mais planos de discagem.

8. (Opcional) No campo **Prefixo de acesso externo**, especifique um valor somente se os usuários precisarem discar um ou mais dígitos iniciais adicionais (por exemplo, 9) para obter uma linha externa. É possível digitar um valor de prefixo de até quatro caracteres (#, * e 0 a 9).

    > [!NOTE]
    > Se você especificar um prefixo de acesso externo, não será necessário criar uma nova regra de normalização para acomodar o prefixo.

9. Associe e configure as regras de normalização para o plano de discagem da seguinte maneira:

    - Para escolher uma ou mais regras de uma lista de todas as regras de normalização disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Em **Selecionar as Regras de Normalização**, realce as regras que você deseja associar ao plano de discagem e clique em **OK**.

   - Para definir uma nova regra de normalização e associá-la ao plano de discagem, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [criar ou modificar uma regra de normalização no Skype para negócios](normalization-rules.md).

   - Para editar uma regra de normalização que já está associada ao plano de discagem, realce o nome da regra e clique em **Mostrar detalhes**.

   - Para copiar uma regra de normalização existente a fim de usá-la como um ponto de partida para a definição de uma nova regra, realce o nome da regra e clique em **Copiar** e clique em **Colar**.

   - Para remover uma regra de normalização do plano de discagem, realce o nome da regra e clique em **Remover**.

     > [!NOTE]
     > Cada plano de discagem deve ter no mínimo uma regra de normalização associada. Para obter informações sobre como determinar a todas as regras de normalização um dial plan requer, consulte o [plano de voz de saída de roteamento no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) na documentação de planejamento.

10. Verifique se que as regras de normalização do plano de discagem são organizadas na ordem correta. Para alterar a posição de uma regra na lista, destaque o nome da regra e clique em cima ou seta para baixo.

    > [!IMPORTANT]
    > Skype para Business Server percorre a lista de regras de normalização de cima para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um plano de discagem de modo que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas. > A regra de normalização padrão **Manter todos** ^(\d{11})$ corresponde a qualquer número de 11 dígitos. Por exemplo, se você adicionar uma regra de normalização que faz a correspondência de números de 11 dígitos que começam com 1425, certifique-se de **Manter todos** é classificado abaixo mais restritivo ^(1425\d{7}) regra$.

11. (Opcional) Insira um número para testar o plano de discagem e, em seguida, clique em  **Ir**. Os resultados do teste são exibidos em  **Insira um número de teste**.

12. Clique em **OK**.

13. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que você criar um plano de discagem, será necessário executar o comando **Confirmar tudo** para publicar a alteração na configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.

### <a name="to-modify-a-dial-plan"></a>Para modificar um plano de discagem

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em  **Plano de Discagem**.

4. Na página **Plano de Discagem**, dê um duplo clique no nome de um plano de discagem.

    > [!NOTE]
    > O escopo e o nome do plano de discagem foram definidos quando o plano de discagem foi criado. Eles não podem ser alterados.

5. (Opcional) Em **Editar Plano de Discagem**, edite o campo **Nome simples**, que é pré-preenchido com o mesmo nome que aparece no campo  **Nome** para especificar um nome mais descritivo que reflita o site, serviço ou usuário para o qual o plano de discagem se aplica.

    > [!IMPORTANT]
    > O **nome simples** deve ser exclusivo entre todos os planos de discagem na implantação do Lync Server 2013. Ele não pode exceder 256 caracteres Unicode, cada um deles pode ser um caractere de caracteres alfabético ou numérico, um hífen (-), um ponto (.), um sinal de adição (+) ou um sublinhado (_). > não são permitidos espaços no campo **nome Simple** .

6. (Opcional) No campo **Descrição**, digite informações descritivas sobre o plano de discagem.

7. (Opcional) Se você quiser usar esse plano de discagem como uma região para números de acesso de discagem, especifique uma **Região de conferência de discagem**. Se você não quiser usar esse plano de discagem para números de acesso de discagem, deixe esse campo vazio.

    > [!NOTE]
    > As regiões de conferência d discagem são necessárias para associar números de acesso de conferência discada a um ou mais planos de discagem.

8. (Opcional) No campo **Prefixo de acesso externo**, especifique um valor somente se usuários precisarem discar um ou mais dígitos primeiro para obter uma linha externa (por exemplo, 9). Você pode digitar um valor de prefixo de até quatro caracteres (isto é, #, * e 0-9).

    > [!NOTE]
    > Se você especificar um prefixo de acesso externo, não será necessário criar uma nova regra de normalização para acomodar o prefixo.

9. Associe e configure regras de normalização para o plano de discagem:

   - Para escolher uma ou mais regras de uma lista de todas as regras de normalização disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Na caixa de diálogo **Selecionar Regras de Normalização**, destaque as regras que deseja associar ao plano de discagem e clique em **OK**.

   - Para definir uma nova regra de normalização e associá-la ao plano de discagem, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [criar ou modificar uma regra de normalização no Skype para negócios](normalization-rules.md).

   - Para editar uma regra de normalização que já está associada ao plano de discagem, realce o nome da regra e clique em **Mostrar detalhes**.

   - Para copiar uma regra de normalização existente a fim de usá-la como um ponto de partida para a definição de uma nova regra, realce o nome da regra e clique em **Copiar** e clique em **Colar**.

   - Para remover uma regra de normalização do plano de discagem, realce o nome da regra e clique em **Remover**.

    > [!NOTE]
    > Cada plano de discagem deve ter no mínimo uma regra de normalização associada. Para obter detalhes sobre como determinar a todas as regras de normalização um dial plan requer, consulte o [plano de voz de saída de roteamento no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) na documentação de planejamento.

10. Verifique se que as regras de normalização do plano de discagem são organizadas na ordem correta. Para alterar a posição de uma regra na lista, destaque o nome da regra e clique em cima ou seta para baixo.

    > [!IMPORTANT]
    > Skype para Business Server percorre a lista de regras de normalização de cima para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um plano de discagem de modo que um número discado possa corresponder a mais de uma regra de normalização, certifique-se de que as regras mais restritivas sejam classificadas acima das menos restritivas. > A regra de normalização padrão **Manter todos** ^(\d{11})$ corresponde a qualquer número de 11 dígitos. Se, por exemplo, você pode adicionar uma regra de normalização que faz a correspondência de números de 11 dígitos que começam com 1425, certifique-se de **Manter todos** é classificado abaixo mais restritivo ^(1425\d{7}) regra$.

11. (Opcional) Insira um número para testar o plano de discagem e, em seguida, clique em  **Ir**. Os resultados do teste são exibidos em  **Insira um número de teste**.

    > [!NOTE]
    > É possível salvar um plano de discagem que não passou ainda no teste e reconfigurá-lo mais tarde. Para obter detalhes, consulte [Roteamento de voz de teste](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

12. Clique em **OK**.

13. Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou modificar um plano de discagem, você deve executar o comando  **Confirmar tudo** para publicar as alterações de configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.

## <a name="see-also"></a>Consulte também

[Publicar alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md)

