---
title: Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Resumo: crie ou modifique as políticas de voz e configure os registros de uso de PSTN usando o painel de controle do Skype for Business Server.'
ms.openlocfilehash: b9024ea1efac7f58fea7175f22f85b325ab5a43c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300891"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business

**Resumo:** Crie ou modifique as políticas de voz e configure os registros de uso de PSTN usando o painel de controle do Skype for Business Server.

> [!NOTE]
> Cada política de voz precisa ter pelo menos um registro de uso de Rede Telefônica Pública Comutada (PSTN) associada. Para ver uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice e exibir suas propriedades, consulte [exibir registros de uso de PSTN no Skype for Business](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>Para criar uma política de voz

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.

3. Na página **Política de Voz**, clique em **Novo** e selecione um escopo para a nova política:

   - **Política do site** se aplica a todo um site, exceto algum usuário ou grupo que tenha recebido uma política de usuário. Se você selecionar Site para um escopo de política, escolha o site na caixa de diálogo **Selecionar um Site**. Se uma política de voz tiver sido criada para um site, o site não aparece na caixa de diálogo **Selecionar um Site**.

   - **Política de usuário** pode ser aplicada a usuários ou grupos especificados.

4. Se o escopo da política de voz for Usuário, digite um nome descritivo para a política no campo **Nome**.

    > [!NOTE]
    > Se o escopo da política de voz for Site, o campo **Nome** na **Nova Política de Voz** será pré-preenchido com o nome do site e não poderá ser alterado.

5. (Opcional) Insira informações descritivas adicionais para a política de voz.

6. Marque ou desmarque as caixas de seleção a seguir para habilitar ou desabilitar cada um dos **Recursos de chamada** para esta política de voz:

   - O **recurso de mensagem de voz** impede que chamadas sejam roteadas imediatamente para o sistema de caixa postal do celular do usuário quando o toque simultâneo está configurado e o telefone está desligado, fora da bateria ou fora do alcance.

     > [!NOTE]
     > Esse recurso só é configurável por meio do Shell de gerenciamento do Skype for Business Server

   - **Encaminhamento de chamadas** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. O Skype for Business Server oferece uma variedade significativamente maior de opções de configuração para encaminhamento de chamadas. Por exemplo, se uma organização não deseja permitir que chamadas de entrada sejam encaminhadas externamente à PSTN, um administrador por aplicar uma política especial de voz para implantar esta restrição. Habilitado por padrão.

   - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. No Skype for Business Server, um representante pode configurar o toque simultâneo que permite que as chamadas recebidas para seu gerente sejam chamadas para todos os alvos de toque simultâneos do representante. Isso oferece uma maior flexibilidade ao delegado em responder chamadas direcionadas ao gerente. Habilitado por padrão.

   - A **transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.

   - **Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.

   - **Toque simultâneo** permite que as chamadas recebidas toquem em telefones adicionais (por exemplo, um celular) ou outros dispositivos de pontos de extremidade. O Skype for Business Server oferece uma gama significativamente mais ampla de opções de configuração para toque simultâneo. Habilitado por padrão.

   - A **chamada de equipe** permite que os usuários de uma equipe definida atendam às chamadas de outros membros da equipe. Habilitado por padrão.

   - O **Redirecionamento de PSTN** permite que as chamadas realizadas por usuários que receberam essa política para outros usuários empresariais sejam redirecionadas na PSTN se a WAN estiver congestionada ou indisponível. Habilitado por padrão.

   - A **substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamadas de um usuário específico. Desabilitada por padrão.

     > [!NOTE]
     > A política será substituída somente para chamadas de entrada para o usuário e não para chamadas de saída feitas pelo usuário. Após o estabelecimento da sessão, o consumo de largura de banda será registrado de forma precisa. Essa configuração deve ser usada com moderação e deve ser reservado em prol de decisões apropriadas de controle de chamada.

   - **Rastreamento de chamada mal-intencionada** permite que os usuários reportem chamadas mal intencionadas (como ameaças) usando a UI do cliente, o que por sua vez marca as chamadas nos Registros de Detalha de Chamada (CDRs). Desabilitado por padrão.

   - **Opções de ocupado** habilita ou desabilita as opções de ocupação para a política de voz especificada. As opções de ocupado permitem que as chamadas recebidas sejam roteadas para a caixa postal ou recusadas com um sinal de ocupado quando o usuário de destino da chamada estiver no telefone. Opções de ocupado é uma nova política de voz introduzida na atualização cumulativa de julho de 2016. A verificação desse parâmetro permite opções ocupadas e a desmarcação desabilita as opções ocupadas. Para obter mais informações, consulte [planejar opções ocupadas para o Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) e [instalar e configurar opções de ocupação para o Skype for Business Server](install-and-configure-busy-options.md).

7. Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:

   - Para escolher um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de voz e clique em **OK**.

   - Para remover um registro de uso de PSTN desta política de voz, realce o registro e clique em **Remover**.

   - Para definir um novo registro de uso PSTN e associá-lo a essa política de voz, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, digite um nome descritivo para o registro. Por exemplo, talvez você queira criar um registro de uso de PSTN namedRedmond para funcionários em tempo integral localizados em Redmond e outro namedRedmondTemps para funcionários temporários.

     > [!NOTE]
     > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, realce a rota e então clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.

     d. Clique em **OK**.

   - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:

     a. Realce o registro de uso do PSTN que você deseja editar e então clique em **Mostrar detalhes**.

     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota desse registro de uso do PSTN, realce a rota e então clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.

     c. Clique em **OK**.

8. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome do registro e clique na seta para cima ou para baixo.

    > [!IMPORTANT]
    > A ordem na qual PSTN registros de uso são listados na diretiva de voz é significativa. O Skype for Business Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Para associar e configurar registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo nesta política de voz, execute um destes procedimentos:

   - Para usar os mesmos registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo que esta política de voz, selecione a opção **Encaminhar usando os usos de PSTN da chamada** no menu suspenso.

   - Para permitir o encaminhamento de chamadas e o toque simultâneo somente para usuários internos do Skype for Business, selecione a opção **rota para usuários internos do Skype for Business somente** no menu suspenso. Calls will not be forwarded to external PSTN numbers.

   - Para especificar registros de uso de PSTN diferentes para encaminhamento de chamadas e toque simultâneos que os usados para esta política de voz, selecione a opção **Encaminhar usando usos de PSTN personalizados** no menu suspenso. Essa opção exibe um controle para selecionar registros de uso de PSTN existentes ou criar novos registros de uso de PSTN especificamente para encaminhamento de chamadas e toque simultâneo.

   - Para selecionar um ou mais registros de uma lista de registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de encaminhamento de chamada e toque simultâneo, e então clique em **OK**.

   - Para remover um registro de uso de PSTN desta política de encaminhamento de chamadas e toque simultâneo, realce o registro e clique em **Remover**.

   - Para definir um novo registro de uso de PSTN e associá-lo a esta política de encaminhamento de chamadas e toque simultâneo, siga estes passos:

     a. Clique em **Novo**.

     b. No campo **Nome**, digite um nome descritivo para o registro.

     > [!NOTE]
     > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.

     d. Clique em **OK**.

   - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:

     a. Realce o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.

     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.

     c. Clique em **OK**.

10. (Opcional) Insira um número para testar a política de voz e clique em **Ir**. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.

11. Clique em **OK**.

12. Na página **Política de Voz**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que você criar ou modificar uma política de voz, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.

13. Adicionais O escape de correio de voz detecta que uma chamada foi imediatamente respondida pela caixa postal do celular do usuário e desconecta a chamada para a caixa postal do celular. Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário dando ao usuário a oportunidade de atender a chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configurar o recurso de mensagem de voz no Skype for Business](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>Para modificar uma política de voz

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.

3. Na página **Política de Voz**, clique duas vezes em um nome de política de voz.

    > [!NOTE]
    > O escopo e o nome foram definidos quando a política de voz foi criada. Eles não podem ser alterados.

4. (Opcional) Em **Editar Política de Voz**, digite as informações descritivas adicionais para a política de voz.

5. Marque ou desmarque as seguintes caixas de seleção para habilitar ou desabilitar cada um dos **Recursos de chamada**:

   - O **recurso de mensagem de voz** impede que chamadas sejam roteadas imediatamente para o sistema de caixa postal do celular do usuário quando o toque simultâneo está configurado e o telefone está desligado, fora da bateria ou fora do alcance.

     > [!NOTE]
     > Esse recurso só é configurável por meio do Shell de gerenciamento do Skype for Business Server

   - **Encaminhamento de chamadas** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. O Skype for Business Server oferece uma variedade significativamente maior de opções de configuração para encaminhamento de chamadas. Por exemplo, se uma organização não deseja permitir que chamadas de entrada sejam encaminhadas externamente à PSTN, um administrador por aplicar uma política especial de voz para implantar esta restrição. Habilitado por padrão.

   - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. No Skype for Business Server, um representante pode configurar o toque simultâneo que permite que as chamadas recebidas para seu gerente sejam chamadas para todos os alvos de toque simultâneos do representante. Isso oferece uma maior flexibilidade ao delegado em responder chamadas direcionadas ao gerente. Habilitado por padrão.

   - A **transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.

   - **Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.

   - **Toque simultâneo** permite que as chamadas recebidas toquem em telefones adicionais (por exemplo, um celular) ou outros dispositivos de pontos de extremidade. O Skype for Business Server oferece uma gama significativamente mais ampla de opções de configuração para toque simultâneo. Habilitado por padrão.

   - A **chamada de equipe** permite que os usuários de uma equipe definida atendam às chamadas de outros membros da equipe. Habilitado por padrão.

   - O **Redirecionamento de PSTN** permite que as chamadas realizadas por usuários que receberam essa política para outros usuários empresariais sejam redirecionadas na PSTN se a WAN estiver congestionada ou indisponível. Habilitado por padrão.

   - A **substituição da política de largura de banda** permite que os administradores substituam as decisões da política de CAC de um usuário específico. Desabilitada por padrão.

     > [!NOTE]
     > A política será substituída apenas para chamadas em entrada do usuário e não para chamadas em saída realizadas pelo usuário. Após a sessão ser estabelecida, o consumo de largura de banda será precisamente registrado. Esta configuração deve ser usada com moderação.

   - **Rastreamento de chamada mal-intencionada** permite que os usuários reportem chamadas mal intencionadas (como ameaças) usando a UI do cliente, o que por sua vez marca as chamadas nos CDRs. Desabilitado por padrão.

6. Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:

   - Para escolher um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de voz e clique em **OK**.

   - Para remover um registro de uso de PSTN desta política de voz, realce o registro e clique em **Remover**.

   - Para definir um novo registro de uso PSTN e associá-lo a essa política de voz, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, digite um nome descritivo para o registro. Por exemplo, talvez você queira criar um registro de uso de PSTN namedRedmond para funcionários em tempo integral localizados em Redmond e outro registro namedRedmondTemps para funcionários temporários.

     > [!NOTE]
     > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.

     d. Clique em **OK**.

   - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:

     a. Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.

     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.

     c. Clique em **OK**.

7. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome do registro e clique na seta para cima ou para baixo.

    > [!NOTE]
    > A ordem na qual PSTN registros de uso são listados na diretiva de voz é significativa. O Skype for Business Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Para associar e configurar registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo nesta política de voz, execute um destes procedimentos:

   - Para usar os mesmos registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo que esta política de voz, selecione a opção **Encaminhar usando os usos de PSTN da chamada** no menu suspenso.

   - Para permitir o encaminhamento de chamadas e o toque simultâneo somente para usuários internos do Skype for Business, selecione encaminhar **para usuários internos do Skype for Business somente** no menu suspenso. Calls will not be forwarded to external PSTN numbers.

   - Para usar registros de uso do PSTN diferentes dos usados nesta política de voz para encaminhamento de chamadas e toque simultâneo, selecione a opção **Rotear com usos de PSTN personalizados** no menu suspenso. Esta opção exibe um controle para selecionar registros de uso do PSTN existentes ou criar novos registros de uso do PSTN, especificamente para encaminhamento de chamadas e toques simultâneos.

   - Para selecionar um ou mais registros de uma lista de registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de encaminhamento de chamada e toque simultâneo, e então clique em **OK**.

   - Para remover um registro de uso de PSTN desta política de encaminhamento de chamadas e toque simultâneo, realce o registro e clique em **Remover**.

   - Para definir um novo registro de uso de PSTN e associá-lo a esta política de encaminhamento de chamadas e toque simultâneo, siga estes passos:

     a. Clique em **Novo**.

     b. No campo **Nome**, digite um nome descritivo para o registro.

     > [!NOTE]
     > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.

   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     d. Clique em **OK**.

   - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:

     a. Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.

     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

     - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

     - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.

     - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

     - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).

     c. Clique em **OK**.

9. (Opcional) Insira um número para testar a política de voz e clique em **Ir**. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.

10. Clique em **OK**.

11. Na página **Política de Voz**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou modificar uma política de voz, você deve executar o comando **Confirmar todos** para publicar a alteração da configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.

12. Adicionais O escape de correio de voz detecta que uma chamada foi imediatamente respondida pela caixa postal do celular do usuário e desconecta a chamada para a caixa postal do celular. Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário dando ao usuário a oportunidade de atender a chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configurar o recurso de mensagem de voz no Skype for Business](configure-voice-mail-escape.md).

## <a name="see-also"></a>Confira também

[Exibir registros de uso de PSTN no Skype for Business](view-pstn-usage-records.md)

[Criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md)

[Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md)

[Configurar o recurso de mensagem de voz no Skype for Business](configure-voice-mail-escape.md)

