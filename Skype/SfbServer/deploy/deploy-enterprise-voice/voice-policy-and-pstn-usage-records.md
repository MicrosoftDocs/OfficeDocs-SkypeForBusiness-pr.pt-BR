---
title: Criar ou modificar uma política de voz e configurar registros de uso PSTN em Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Resumo: crie ou modifique políticas de voz e configure registros de uso PSTN usando o painel de Skype for Business Server Controle.'
ms.openlocfilehash: 0188881fe91d527c64b95a8cac49ba91ed12bf5f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769599"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Criar ou modificar uma política de voz e configurar registros de uso PSTN em Skype for Business

**Resumo:** Crie ou modifique políticas de voz e configure registros de uso de PSTN usando o painel Skype for Business Server Controle.

> [!NOTE]
> Cada política de voz deve ter pelo menos um registro de uso da PSTN (Rede Telefônica Pública Comugada). Para ver uma listagem de todos os registros de uso PSTN disponíveis em sua implantação Enterprise Voice e exibir suas propriedades, consulte [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>Para criar uma política de voz

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.

3. Na página **Política de Voz**, clique em **Novo** e selecione um escopo para a nova política:

   - **Política do site** se aplica a todo um site, exceto algum usuário ou grupo que tenha recebido uma política de usuário. Se você selecionar Site para um escopo de política, escolha o site na caixa de diálogo **Selecionar um Site**. Se uma política de voz tiver sido criada para um site, o site não aparece na caixa de diálogo **Selecionar um Site**.

   - **Política de usuário** pode ser aplicado a usuários ou grupos especificados.

4. Se o escopo da política de voz for Usuário, digite um nome descritivo para a política no campo **Nome**.

    > [!NOTE]
    > Se o escopo da política de voz for Site, o campo **Nome** na **Nova Política de Voz** será pré-preenchido com o nome do site e não poderá ser alterado.

5. (Opcional) Insira informações descritivas adicionais para a política de voz.

6. Marque ou desmarque as caixas de seleção a seguir para habilitar ou desabilitar cada um dos **Recursos de chamada** para esta política de voz:

   - **A saída de** caixa postal impede que as chamadas são roteadas imediatamente para o sistema de caixa postal do telefone celular do usuário quando o toque simultâneo é configurado e o telefone está desligado, sem bateria ou fora do intervalo.

     > [!NOTE]
     > Esse recurso só é configurável por meio do Shell Skype for Business Server Gerenciamento

   - **Encaminhamento de chamada** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. Skype for Business Server fornece uma variedade significativamente maior de opções de configuração para encaminhamento de chamada. Por exemplo, se uma organização não deseja permitir que as chamadas recebidas sejam encaminhadas externamente à PSTN, um administrador pode aplicar um política de voz especial para implantar essa restrição. Habilitado por padrão.

   - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. No Skype for Business Server, um representante pode configurar o toque simultâneo que permite que as chamadas de entrada para seu gerente toquem todos os destinos simultâneos de toque do representante. Com isso, o representante tem mais flexibilidade para atender a chamadas direcionadas ao gerente. Habilitado por padrão.

   - **Transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.

   - **Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.

   - **Toque simultâneo** permite as chamadas em entrada tocarem em telefones adicionais (por exemplo, um telefone celular) ou outros dispositivos de ponto de extremidade. Skype for Business Server fornece uma variedade significativamente maior de opções de configuração para toque simultâneo. Habilitado por padrão.

   - **Chamada de equipe** permite que os usuários de uma equipe definida respondam às chamadas de outros membros da equipe. Habilitado por padrão.

   - **A re-rotação PSTN** permite que as chamadas feitas por usuários atribuídos a essa política a outros usuários corporativos sejam redirecionadas no PSTN se a WAN estiver congestionada ou indisponível. Habilitado por padrão.

   - **Substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamada para um usuário específico. Desabilitada por padrão.

     > [!NOTE]
     > A política será substituída somente para chamadas de entrada para o usuário e não para chamadas de saída feitas pelo usuário. Após o estabelecimento da sessão, o consumo de largura de banda será registrado de forma precisa. Essa configuração deve ser usada com moderação e deve ser reservado em prol de decisões apropriadas de controle de chamada.

   - **O rastreamento de chamadas** mal-intencionadas permite que os usuários reportem chamadas mal-intencionadas (como ameaças) usando a interface do usuário do cliente, que, por sua vez, sinaliza as chamadas nos Registros de Detalhes de Chamadas (CDRs). Desabilitado por padrão.

   - **As opções de** ocupado habilitam ou desabilitam opções de ocupado para a política de voz especificada. Opções de ocupado permite que as chamadas de entrada sejam roteados para a caixa postal ou rejeitadas com um sinal de ocupado quando o usuário de destino da chamada estiver no telefone. Opções de Ocupado é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016. A verificação desse parâmetro habilita Opções de Ocupado e desmarcar desabilita As Opções de Ocupado. Para obter mais informações, consulte [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and Install and configure Busy Options for [Skype for Business Server](install-and-configure-busy-options.md).

7. Para associar e configurar os registros de uso PSTN para esta política de voz, faça um dos seguintes:

   - Para selecionar um ou mais registros em uma lista de todos os registros de uso do PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que deseja associar a esta política de voz e clique em **OK**.

   - Para remover um registro de uso PSTN desta política de voz, destaque o registro e clique em **Remover**.

   - Para definir um novo registro de uso PSTN e associá-lo com esta política de voz, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, insira um nome descritivo exclusivo para o registro. Por exemplo, talvez você queira criar um registro de uso PSTN chamadoRedmond para funcionários em tempo integral localizados em Redmond e outro chamadoRedmondTemps para funcionários temporários.

     > [!NOTE]
     > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, realce a rota e então clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**.

     d. Clique em **OK**.

   - Para editar um registro de uso do PSTN que já está associado a essa política de voz, faça o seguinte:

     a. Realce o registro de uso do PSTN que você deseja editar e então clique em **Mostrar detalhes**.

     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota desse registro de uso do PSTN, realce a rota e então clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.

     c. Clique em **OK**.

8. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realça o nome do registro e clique na seta para cima ou para baixo.

    > [!IMPORTANT]
    > A ordem na qual os registros de uso PSTN são listados na política de voz é significante. Skype for Business Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:

   - Para usar os mesmos registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo como esta política de voz, selecione a opção **Rotear com usos de PSTN de chamada** no menu suspenso.

   - Para permitir o encaminhamento de chamada e toque simultâneo para usuários internos Skype for Business, selecione **a** opção Rotear para usuários internos Skype for Business somente no menu suspenso. As chamadas não serão encaminhadas para números PSTN externos.

   - Para especificar registros de uso de PSTN diferentes para encaminhamento de chamadas e toque simultâneos que os usados para esta política de voz, selecione a opção **Encaminhar usando usos de PSTN personalizados** no menu suspenso. Essa opção exibe um controle para selecionar registros de uso de PSTN existentes ou criar novos registros de uso de PSTN especificamente para encaminhamento de chamadas e toque simultâneo.

   - Para selecionar um ou mais registros de uma lista de registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de encaminhamento de chamada e toque simultâneo, e então clique em **OK**.

   - Para remover um registro de uso do PSTN desta política de encaminhamento de chamadas e toques simultâneos, realce o registro e clique em **Remover**.

   - Para definir um novo registro de uso do PSTN e associá-lo a essa política de encaminhamento de chamadas e toques simultâneos, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, insira um nome descritivo exclusivo para o registro.

     > [!NOTE]
     > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**.

     d. Clique em **OK**.

   - Para editar um registro de uso do PSTN que já está associado a essa política de voz, faça o seguinte:

     a. Realce o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.

     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**.

     c. Clique em **OK**.

10. (Opcional) Insira um número para testar a política de voz e clique em **Ir**. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.

11. Clique em **OK**.

12. Na página **Política de Voz**, clique em **Confirmar** e em **Confirmar todos**.

    > [!NOTE]
    > Sempre que você criar ou modificar uma política de voz, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, [consulte Publicar alterações pendentes na](voice-route-config-changes.md) configuração de roteamento de voz Skype for Business na documentação Operações.

13. (Opcional) A Caixa Postal Escape detecta que uma chamada foi atendida imediatamente pela caixa postal do celular do usuário e desconecta a chamada para a caixa postal do celular. Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário, dando ao usuário a oportunidade de responder à chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>Para modificar uma política de voz

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Política de Voz**.

3. Na página **Política de Voz**, clique duas vezes em um nome de política de voz.

    > [!NOTE]
    > O escopo e o nome foram definidos quando a política de voz foi criada. Eles não podem ser alterados.

4. (Opcional) Em **Editar Política de Voz**, digite as informações descritivas adicionais para a política de voz.

5. Marque ou desmarque as seguintes caixas de seleção para habilitar ou desabilitar cada um dos **Recursos de chamada**:

   - **A saída de** caixa postal impede que as chamadas são roteadas imediatamente para o sistema de caixa postal do telefone celular do usuário quando o toque simultâneo é configurado e o telefone está desligado, sem bateria ou fora do intervalo.

     > [!NOTE]
     > Esse recurso só é configurável por meio do Shell Skype for Business Server Gerenciamento

   - **Encaminhamento de chamada** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. Skype for Business Server fornece uma variedade significativamente maior de opções de configuração para encaminhamento de chamada. Por exemplo, se uma organização não deseja permitir que as chamadas recebidas sejam encaminhadas externamente à PSTN, um administrador pode aplicar um política de voz especial para implantar essa restrição. Habilitado por padrão.

   - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. No Skype for Business Server, um representante pode configurar o toque simultâneo que permite que as chamadas de entrada para seu gerente toquem todos os destinos simultâneos de toque do representante. Com isso, o representante tem mais flexibilidade para atender a chamadas direcionadas ao gerente. Habilitado por padrão.

   - **Transferência de chamadas** permite os usuários transferirem chamadas para outros usuários. Habilitado por padrão.

   - **Estacionamento de chamada** permite os usuários estacionarem chamadas em espera e responderem a chamada de um telefone ou cliente diferente. Desabilitado por padrão.

   - **Toque simultâneo** permite as chamadas em entrada tocarem em telefones adicionais (por exemplo, um telefone celular) ou outros dispositivos de ponto de extremidade. Skype for Business Server fornece uma variedade significativamente maior de opções de configuração para toque simultâneo. Habilitado por padrão.

   - **Chamada de equipe** permite que os usuários de uma equipe definida respondam às chamadas de outros membros da equipe. Habilitado por padrão.

   - **A re-rotação PSTN** permite que as chamadas feitas por usuários atribuídos a essa política a outros usuários corporativos sejam redirecionadas no PSTN se a WAN estiver congestionada ou indisponível. Habilitado por padrão.

   - **A substituição da política de** largura de banda permite que os administradores substituam as decisões de política do CAC para um usuário específico. Desabilitado por padrão.

     > [!NOTE]
     > A política será substituída apenas para chamadas em entrada do usuário e não para chamadas em saída realizadas pelo usuário. Após a sessão ser estabelecida, o consumo de largura de banda será precisamente registrado. Esta configuração deve ser usada com moderação.

   - **O rastreamento de chamadas** mal-intencionadas permite que os usuários reportem chamadas mal-intencionadas (como ameaças) usando a interface do usuário do cliente, que, por sua vez, sinaliza as chamadas nas CDRs. Desabilitado por padrão.

6. Para associar e configurar os registros de uso PSTN para esta política de voz, faça um dos seguintes:

   - Para selecionar um ou mais registros em uma lista de todos os registros de uso do PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que deseja associar a esta política de voz e clique em **OK**.

   - Para remover um registro de uso PSTN desta política de voz, destaque o registro e clique em **Remover**.

   - Para definir um novo registro de uso PSTN e associá-lo com esta política de voz, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, insira um nome descritivo exclusivo para o registro. Por exemplo, talvez você queira criar um registro de uso PSTN chamadoRedmond para funcionários em tempo integral localizados em Redmond e outro registro chamadoRedmondTemps para funcionários temporários.

     > [!NOTE]
     > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**.

     d. Clique em **OK**.

   - Para editar um registro de uso do PSTN que já está associado a essa política de voz, faça o seguinte:

     a. Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.

     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**.

     c. Clique em **OK**.

7. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realça o nome do registro e clique na seta para cima ou para baixo.

    > [!NOTE]
    > A ordem na qual os registros de uso PSTN são listados na política de voz é significante. Skype for Business Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:

   - Para usar os mesmos registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo como esta política de voz, selecione a opção **Rotear com usos de PSTN de chamada** no menu suspenso.

   - Para permitir o encaminhamento de chamada e toque simultâneo  para usuários internos Skype for Business, selecione Rotear para usuários internos Skype for Business somente no menu suspenso. As chamadas não serão encaminhadas para números PSTN externos.

   - Para usar registros de uso do PSTN diferentes dos usados nesta política de voz para encaminhamento de chamadas e toque simultâneo, selecione a opção **Rotear com usos de PSTN personalizados** no menu suspenso. Esta opção exibe um controle para selecionar registros de uso do PSTN existentes ou criar novos registros de uso do PSTN, especificamente para encaminhamento de chamadas e toques simultâneos.

   - Para escolher um ou mais registros de uma lista de todos os registros de uso do PSTN para encaminhamento de chamadas e toques simultâneos, clique em **Selecionar**. Realce os registros que deseja associar a esta política de encaminhamento de chamadas e toques simultâneos e clique em **OK**.

   - Para remover um registro de uso do PSTN desta política de encaminhamento de chamadas e toques simultâneos, realce o registro e clique em **Remover**.

   - Para definir um novo registro de uso do PSTN e associá-lo a essa política de encaminhamento de chamadas e toques simultâneos, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, insira um nome descritivo exclusivo para o registro.

     > [!NOTE]
     > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).

     d. Clique em **OK**.

   - Para editar um registro de uso do PSTN que já está associado a essa política de voz, faça o seguinte:

     a. Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.

     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

     - Para escolher um ou mais rotas na lista de todas as rotas disponíveis na sua implantação do Enterprise Voice, clique em **Selecionar**, destaque as rotas que deseja associar com este registro de uso PSTN e clique em **OK**.

     - Para remover uma rota deste registro de uso PSTN, destaque a rota e clique em **Remover**.

     - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

     - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).

     c. Clique em **OK**.

9. (Opcional) Insira um número para testar a política de voz e clique em **Ir**. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.

10. Clique em **OK**.

11. Na página **Política de Voz**, clique em **Confirmar** e em **Confirmar todos**.

    > [!NOTE]
    > Sempre que criar ou modificar uma política de voz, você deve executar o comando **Confirmar todos** para publicar a alteração da configuração. Para obter detalhes, [consulte Publicar alterações pendentes na](voice-route-config-changes.md) configuração de roteamento de voz Skype for Business na documentação Operações.

12. (Opcional) A Caixa Postal Escape detecta que uma chamada foi atendida imediatamente pela caixa postal do celular do usuário e desconecta a chamada para a caixa postal do celular. Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário, dando ao usuário a oportunidade de responder à chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).

## <a name="see-also"></a>Confira também

[Exibir registros de uso de PSTN em Skype for Business](view-pstn-usage-records.md)

[Criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md)

[Publicar alterações pendentes na configuração de roteamento de voz Skype for Business](voice-route-config-changes.md)

[Configurar a saída de caixa postal no Skype for Business](configure-voice-mail-escape.md)