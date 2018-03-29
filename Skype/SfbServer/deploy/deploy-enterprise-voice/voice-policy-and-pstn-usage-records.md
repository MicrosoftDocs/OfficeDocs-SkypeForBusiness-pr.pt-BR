---
title: Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Resumo: Criar ou modificar políticas de voz e configurar registros de uso PSTN usando o Skype para painel de controle do servidor de negócios.'
ms.openlocfilehash: 148b3762d0055a96bf10a4fbee907d88b42f28ed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business-2015"></a>Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype for Business 2015
 
**Resumo:** Criar ou modificar políticas de voz e configurar registros de uso PSTN usando o Skype para painel de controle do servidor de negócios.
  
> [!NOTE]
> Cada política de voz precisa ter pelo menos um registro de uso de Rede Telefônica Pública Comutada (PSTN) associada. Para ver uma lista de todos os registros de uso PSTN disponíveis em sua implantação do Enterprise Voice e exibir suas propriedades, consulte [View PSTN usage records no Skype para negócios 2015](view-pstn-usage-records.md). 
  
### <a name="to-create-a-voice-policy"></a>Para criar uma política de voz

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.
    
3. Na página **Política de Voz**, clique em **Novo** e selecione um escopo para a nova política:
    
   - **Política do site** se aplica a todo um site, exceto algum usuário ou grupo que tenha recebido uma política de usuário. Se você selecionar Site para um escopo de política, escolha o site na caixa de diálogo **Selecionar um Site**. Se uma política de voz tiver sido criada para um site, o site não aparece na caixa de diálogo **Selecionar um Site**.
    
   - **Política de usuário** pode ser aplicada a usuários ou grupos especificados.
    
4. Se o escopo da política de voz for Usuário, digite um nome descritivo para a política no campo **Nome**.
    
    > [!NOTE]
    > Se o escopo da política de voz for Site, o campo **Nome** na **Nova Política de Voz** será pré-preenchido com o nome do site e não poderá ser alterado.
  
5. (Opcional) Insira informações descritivas adicionais para a política de voz.
    
6. Marque ou desmarque as caixas de seleção a seguir para habilitar ou desabilitar cada um dos **Recursos de chamada** para esta política de voz:
    
   - **Escape da caixa postal** evita que as chamadas imediatamente sendo roteados para o sistema de correio de voz de celular do usuário, quando o toque simultâneo é configurado e o telefone estiver desativado, fora da bateria ou fora do intervalo.
    
    > [!NOTE]
    > Esse recurso é configurável apenas através do Skype do Shell de gerenciamento do servidor de negócios 
  
   - **Encaminhamento de chamadas** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. Skype para Business Server fornece um intervalo significativamente maior de opções de configuração para encaminhamento de chamadas. Por exemplo, se uma organização não deseja permitir que chamadas de entrada sejam encaminhadas externamente à PSTN, um administrador por aplicar uma política especial de voz para implantar esta restrição. Habilitado por padrão.
    
   - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. Skype para Business Server, um representante pode configurar Toque simultâneo que permite chamadas de entrada para seu gerente para ligar para todos os destinos de Toque simultâneo do representante. Isso oferece uma maior flexibilidade ao delegado em responder chamadas direcionadas ao gerente. Habilitado por padrão.
    
   - A **transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.
    
   - **Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.
    
   - **Toque simultâneo** permite que as chamadas recebidas toquem em telefones adicionais (por exemplo, um celular) ou outros dispositivos de pontos de extremidade. Skype para Business Server fornece um intervalo significativamente maior de opções de configuração de Toque simultâneo. Habilitado por padrão.
    
   - A **chamada de equipe** permite que os usuários de uma equipe definida atendam às chamadas de outros membros da equipe. Habilitado por padrão.
    
   - O **Redirecionamento de PSTN** permite que as chamadas realizadas por usuários que receberam essa política para outros usuários empresariais sejam redirecionadas na PSTN se a WAN estiver congestionada ou indisponível. Habilitado por padrão.
    
   - A **substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamadas de um usuário específico. Desabilitada por padrão.
    
    > [!NOTE]
    > A política será substituída somente para chamadas de entrada para o usuário e não para chamadas de saída feitas pelo usuário. Após o estabelecimento da sessão, o consumo de largura de banda será registrado de forma precisa. Essa configuração deve ser usada com moderação e deve ser reservado em prol de decisões apropriadas de controle de chamada. 
  
   - **Rastreamento de chamada mal-intencionada** permite que os usuários reportem chamadas mal intencionadas (como ameaças) usando a UI do cliente, o que por sua vez marca as chamadas nos Registros de Detalha de Chamada (CDRs). Desabilitado por padrão.
    
   - **Opções de ocupado** habilita ou desabilita as opções de disponibilidade para a política de voz especificada. Opções de ocupado permite que as chamadas recebidas sejam roteadas para a caixa postal ou rejeitada com um sinal de ocupado quando o usuário de destino da chamada estiver no telefone. Opções de disponibilidade é uma nova política de voz introduzida no de 2016 julho atualizações cumulativas. Este parâmetro habilita ocupado opções de verificação e desmarcar desativa opções ocupado. Para obter mais informações, consulte o [plano de ocupado/opções do Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) e [instalar e configurar as opções de disponibilidade do Skype para Business Server](install-and-configure-busy-options.md).
    
7. Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:
    
   - Para escolher um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de voz e clique em **OK**.
    
   - Para remover um registro de uso de PSTN desta política de voz, realce o registro e clique em **Remover**.
    
   - Para definir um novo registro de uso PSTN e associá-lo a essa política de voz, faça o seguinte:
    
    a. Clique em **Novo**.
    
    b. No campo **Nome**, digite um nome descritivo para o registro. Por exemplo, convém criar um namedRedmond de registro de uso do PSTN para funcionários em tempo integral, localizados em Redmond e outro namedRedmondTemps para funcionários temporários.
    
    > [!NOTE]
    > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.
  
    c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
    
   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
    
   - Para remover uma rota do registro de uso do PSTN, realce a rota e então clique em **Remover**.
    
   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md).
    
   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. 
    
    d. Clique em **OK**.
    
   - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:
    
    a. Realce o registro de uso do PSTN que você deseja editar e então clique em **Mostrar detalhes**.
    
    b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
    
   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
    
   - Para remover uma rota desse registro de uso do PSTN, realce a rota e então clique em **Remover**.
    
   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md).
    
   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. 
    
    c. Clique em **OK**.
    
8. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição do registro na lista, destaque o nome de registro e clique em cima ou seta para baixo.
    
    > [!IMPORTANT]
    > A ordem na qual PSTN registros de uso são listados na diretiva de voz é significativa. Skype para Business Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. 
  
9. Para associar e configurar registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo nesta política de voz, execute um destes procedimentos:
    
   - Para usar os mesmos registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo que esta política de voz, selecione a opção **Encaminhar usando os usos de PSTN da chamada** no menu suspenso.
    
   - Para permitir que o encaminhamento de chamadas e toque simultâneo para Skype interna Business somente para usuários, selecione a opção **rota interna Skype Business somente para usuários** no menu suspenso. As chamadas não serão encaminhadas para números PSTN externos.
    
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
    
   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md).
    
   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. 
    
    d. Clique em **OK**.
    
   - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:
    
    a. Realce o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.
    
    b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
    
   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
    
   - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.
    
   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md).
    
   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. 
    
    c. Clique em **OK**.
    
10. (Opcional) Insira um número para testar a política de voz e clique em **Ir**. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.
    
11. Clique em **OK**.
    
12. Na página **Política de Voz**, clique em **Confirmar** e clique em **Confirmar tudo**. 
    
    > [!NOTE]
    > Sempre que você criar ou modificar uma política de voz, será necessário executar o comando **Confirmar tudo** para publicar a alteração de configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios 2015](voice-route-config-changes.md) na documentação operações.
  
13. (Opcional) Escape de caixa postal detecta que uma chamada foi atendida imediatamente por correio de voz de celular do usuário e desconecta a chamada para a correio de voz de celular. Isso permite que a chamada para continuar a ligar para logon do usuário do outros pontos de extremidade dando ao usuário a oportunidade de atender à chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configurar escape da caixa postal no Skype para negócios 2015](configure-voice-mail-escape.md).
    
### <a name="to-modify-a-voice-policy"></a>Para modificar uma política de voz

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.
    
3. Na página **Política de Voz**, clique duas vezes em um nome de política de voz.
    
    > [!NOTE]
    > O escopo e o nome foram definidos quando a política de voz foi criada. Eles não podem ser alterados. 
  
4. (Opcional) Em **Editar Política de Voz**, digite as informações descritivas adicionais para a política de voz.
    
5. Marque ou desmarque as seguintes caixas de seleção para habilitar ou desabilitar cada um dos **Recursos de chamada**:
    
   - **Escape da caixa postal** evita que as chamadas imediatamente sendo roteados para o sistema de correio de voz de celular do usuário, quando o toque simultâneo é configurado e o telefone estiver desativado, fora da bateria ou fora do intervalo.
    
    > [!NOTE]
    > Esse recurso é configurável apenas através do Skype do Shell de gerenciamento do servidor de negócios 
  
   - **Encaminhamento de chamadas** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. Skype para Business Server fornece um intervalo significativamente maior de opções de configuração para encaminhamento de chamadas. Por exemplo, se uma organização não deseja permitir que chamadas de entrada sejam encaminhadas externamente à PSTN, um administrador por aplicar uma política especial de voz para implantar esta restrição. Habilitado por padrão.
    
   - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. Skype para Business Server, um representante pode configurar Toque simultâneo que permite chamadas de entrada para seu gerente para ligar para todos os destinos de Toque simultâneo do representante. Isso oferece uma maior flexibilidade ao delegado em responder chamadas direcionadas ao gerente. Habilitado por padrão.
    
   - A **transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.
    
   - **Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.
    
   - **Toque simultâneo** permite que as chamadas recebidas toquem em telefones adicionais (por exemplo, um celular) ou outros dispositivos de pontos de extremidade. Skype para Business Server fornece um intervalo significativamente maior de opções de configuração de Toque simultâneo. Habilitado por padrão.
    
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
    
    b. No campo **Nome**, digite um nome descritivo para o registro. Por exemplo, convém criar um namedRedmond de registro de uso do PSTN para funcionários em tempo integral, localizados em Redmond e outro namedRedmondTemps de registro para funcionários temporários.
    
    > [!NOTE]
    > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.
  
    c. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
    
   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
    
   - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.
    
   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md).
    
   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. 
    
    d. Clique em **OK**.
    
   - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:
    
    a. Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.
    
    b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
    
   - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
    
   - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.
    
   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md).
    
   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. 
    
    c. Clique em **OK**.
    
7. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição do registro na lista, destaque o nome de registro e clique em cima ou seta para baixo.
    
    > [!NOTE]
    > A ordem na qual PSTN registros de uso são listados na diretiva de voz é significativa. Skype para Business Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. 
  
8. Para associar e configurar registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo nesta política de voz, execute um destes procedimentos:
    
   - Para usar os mesmos registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo que esta política de voz, selecione a opção **Encaminhar usando os usos de PSTN da chamada** no menu suspenso.
    
   - Para permitir que o encaminhamento de chamadas e toque simultâneo para Skype interna Business somente para usuários, selecione **rota interna Skype Business somente para usuários** no menu suspenso. As chamadas não serão encaminhadas para números PSTN externos.
    
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
    
   - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md).
    
   - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz](http://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).
    
    d. Clique em **OK**.
    
   - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:
    
     a. Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.
    
     b. Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
    
     - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
    
     - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.
    
     - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md).
    
     - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz](http://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).
    
     c. Clique em **OK**.
    
9. (Opcional) Insira um número para testar a política de voz e clique em **Ir**. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.
    
10. Clique em **OK**.
    
11. Na página **Política de Voz**, clique em **Confirmar** e clique em **Confirmar tudo**. 
    
    > [!NOTE]
    > Sempre que criar ou modificar uma política de voz, você deve executar o comando **Confirmar todos** para publicar a alteração da configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios 2015](voice-route-config-changes.md) na documentação operações.
  
12. (Opcional) Escape de caixa postal detecta que uma chamada foi atendida imediatamente por correio de voz de celular do usuário e desconecta a chamada para a correio de voz de celular. Isso permite que a chamada para continuar a ligar para logon do usuário do outros pontos de extremidade dando ao usuário a oportunidade de atender à chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configurar escape da caixa postal no Skype para negócios 2015](configure-voice-mail-escape.md).
    
## <a name="see-also"></a>Consulte também

#### 

[Exibir registros de uso PSTN em Skype para negócios 2015](view-pstn-usage-records.md)
  
[Criar ou modificar uma rota de voz no Skype para negócios 2015](create-or-modify-a-voice-route.md)
  
[Publicar alterações pendentes para a configuração de roteamento de voz no Skype para negócios 2015](voice-route-config-changes.md)
  
[Configurar escape da caixa postal no Skype para negócios 2015](configure-voice-mail-escape.md)

