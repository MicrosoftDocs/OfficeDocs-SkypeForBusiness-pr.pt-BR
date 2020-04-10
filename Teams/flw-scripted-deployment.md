---
title: Provisionamento do Microsoft Teams em escala para os Trabalhadores da Linha de Frente
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: Diretrizes sobre como usar scripts para implantar ou provisionar o Microsoft Teams para Trabalhadores da Linha de Frente.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2496656437ddcd7035b9913781c5ebc08b26582e
ms.sourcegitcommit: 9419860f9a1c1dd2c7c444162e1d55d704e19c69
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43207060"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a>Como provisionar o Teams em escala para os Trabalhadores da Linha de Frente

Precisa integrar rapidamente um grande número de usuários ao Microsoft Teams e configurar uma experiência simplificada para eles? Você pode rapidamente provisionar identidades e equipes, além de atribuir todas as políticas relevantes para controlar a experiência do usuário final, através das instruções a seguir.

Nesse passo a passo, você aprenderá como:

- Criar um grande número de usuários.
- Criar um grande número de equipes e configurar os canais apropriados.
- Atribuir licenciamento em escala.
- Criar políticas de envio de mensagens do Teams, políticas de configuração de aplicativos e políticas de permissão de aplicativos apropriados.
- Aplicar essas políticas a usuários em escala.
- Atribuir um grande número de usuários a uma equipe designada.

> [!NOTE]
> Se você revisou estas informações e acha que precisa de ajuda ou tem alguma dúvida, [**clique aqui**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u) para entrar em contato com o Suporte White Glove.

## <a name="prerequisites"></a>Pré-requisitos

Baixe os ativos a partir [deste local](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).

> [!IMPORTANT]
> Os scripts no link acima são fornecidos como estão pela Microsoft, e devem ser modificados para suas necessidades individuais.

## <a name="technical-requirements"></a>Requisitos técnicos

- O locatário deve ter o número adequado de licenças disponíveis que incluam o Microsoft Teams. Caso ainda não tenha essas licenças, siga as instruções aqui para ativar a [avaliação gratuita do Office 365 E1](e1-trial-license.md).
- Ao executar essas etapas o usuário deve estar na função de administrador global ou administrador de usuários no Azure AD.
- Os usuários devem ter direitos para instalar e configurar softwares no computador local.

## <a name="step-by-step-process-overview"></a>Processo passo a passo

1. **Configuração do Ambiente**
    1. Baixar o arquivo ZIP que contém o exemplo de scripts e documentação do PowerShell
    1. Credenciais de configuração
    1. Configurar ambiente local
    1. Configurar os Módulos do PowerShell e as Variáveis de Ambiente
    1. Criar Registro de Aplicativo
1. **Criar e Configurar Equipes**
    1. Criar Equipes
    1. Criar Canais para as Equipes
1. **Criar Políticas do Teams**
    1. Criar Políticas de Mensagens do Teams
    1. Criar Políticas de Configuração de Aplicativos do Teams
    1. Criar Políticas de Permissão de Aplicativos do Teams
1. **Criar e Configurar Usuários**
    1. Criar usuários e grupos de segurança
    1. Atribuir licenciamento a usuários por meio de um licenciamento com base em grupo
1. **Atribuir Usuários e Políticas**
    1. Atribuir usuários ao Teams
    1. Atribuir políticas a usuários e grupos
1. **Testar e validar**
    1. Verificar se há erros
    1. Entrar no Teams com um usuário de teste

## <a name="set-up-your-environment"></a>Configurar ambiente

As etapas a seguir permitem configurar o ambiente:

### <a name="download-zip-file-containing-sample-powershell-scripts"></a>Baixe o arquivo .zip que contém exemplos de scripts do PowerShell

Antes de prosseguir, será necessário baixar os scripts [deste local](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).

### <a name="setup-credentials"></a>Credenciais de Configuração

Neste documento e nos exemplos de scripts, optamos por criar um arquivo de referência contendo as suas credenciais, de forma a facilitar as coisas. Esta técnica elimina a necessidade de autenticar em todos os pontos de extremidade do serviço, mantendo as credenciais em um repositório local. Para executar os scripts subsequentes, é preciso atualizar esse arquivo de referência com as credenciais exclusivas para você e seu ambiente. De dentro de cada script subsequente, as credenciais adequadas são lidas com a função auxiliar chamada de **GetCreds**, e essas credenciais são usadas para se conectar aos vários serviços.

Não é raro que seja exigido diferentes credenciais para diferentes serviços. Por exemplo, você pode ter credenciais diferentes para MicrosoftTeams, AzureAD e MSonline. Nesse caso, você poderá executar SetCred salvando cada arquivo de credencial com seu próprio nome significativo.

Exemplos: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml

> [!NOTE]
> A conta usada para as credenciais não pode exigir MFA.

Aqui está um exemplo de como os vários scripts usam as credenciais salvas para autenticar:

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

Para definir as suas credenciais, complete o seguinte:

1. Localize **SetCreds.ps1** nos ativos de arquivo .zip.
1. No PowerShell execute o script **SetCreds.ps1** para salvar suas credenciais.
    1. Você receberá uma mensagem com "Executando a operação "Export-Clixml"..." e você precisará digitar "Y" para aprovar.

### <a name="configure-the-local-environment"></a>Configurar o ambiente local

1. Localize **SetConfig.ps1** nos ativos de arquivo .zip.
1. No PowerShell, execute o seguinte comando, substituindo as entradas com as informações específicas.
    1. **SetConfig.ps1** -tenantName [seu nome de locatário] -rootPath "[caminho completo para o repositório git]"

Por exemplo: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`

### <a name="configure-powershell-modules-and-environmental-variables"></a>Configurar os módulos do PowerShell e as variáveis de ambiente

Antes de começar, é preciso instalar e se conectar a vários módulos do PowerShell, incluindo Azure AD, MSAL, MSCloudUtils e MicrosoftTeams.

1. Localize **ConfigurePowerShellModules.ps1** nos ativos de arquivo .zip.
1. Edite e substitua as seguintes variáveis de ambiente pelas suas variáveis:
1. No PowerShell, execute o script **ConfigurePowerShellModules.ps1**.

## <a name="create-and-set-up-teams"></a>Criar e configurar equipes

Para se comunicar e colaborar com os trabalhadores da linha de frente, primeiro será necessário estabelecer uma série de equipes e adicionar canais padrão a elas, o que explicaremos a seguir.

### <a name="create-teams"></a>Criar equipes

As equipes são um conjunto de pessoas, conteúdos e ferramentas dentro da organização. Para a maioria das organizações centradas no trabalhador da linha de frente, a melhor prática é ancorar uma equipe a um local físico. Por exemplo, uma equipe para cada um dos seguintes itens:

- Repositório
- Centro de distribuição
- Unidade fabril
- Hospital
- Mercearia

*Discussão de prática recomendada*: ao projetar suas equipes, é importante lembrar das [especificações e limites do Teams](limits-specifications-teams.md). Para organizações menores, uma equipe de toda a organização pode ser usada para agilizar a comunicação e complementar uma estrutura de local físico. Para outros, uma convenção de nomenclatura de equipe com local físico estruturado auxilia na comunicação corporativa com postagem cruzada para várias equipes simultaneamente com facilidade. Por exemplo, você pode pesquisar e postar em todas as equipes com os EUA no nome para apontar todos os locais dos EUA. Mais informações sobre a postagem cruzada podem ser encontradas [aqui](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).

#### <a name="steps-to-create-teams"></a>Etapas para criar equipes

1. Localize o arquivo **Teams Information.csv** nos ativos.
1. Atualize as informações no arquivo **Teams Information.csv** com as informações específicas da sua organização. Lembre-se das nossas melhores práticas acima.
1. Localize o script **CreateTeams.ps1**.
1. No PowerShell, execute o script **CreateTeams.ps1**.

### <a name="create-channels-for-teams"></a>Criar canais para as equipes

Os canais são seções dedicadas dentro de uma equipe para manter as conversas organizadas por disciplinas, projetos, tópicos específicos e muito mais. Cada equipe recebe automaticamente um canal geral, mas a partir daí é possível personalizar sua estrutura de acordo com as necessidades da sua empresa. Por exemplo, a estrutura de canal adicional poderia incluir:

- **Fabricação** – Segurança, Linha 1, Linha 2, Comunicação Corporativa, Treinamento
- **Mercearia** – Padaria, Produção, Carne, Comunicação Corporativa, Treinamento
- **Saúde** – Enfermeiras, Médicos, Unidade de Cuidados Críticos 1, Unidade de Cuidados Críticos 2
- **Hospitalidade** – Recepção, Manutenção, Limpeza, Manobrista e Bagagem, Comunicação Corporativa, Treinamento
- **Varejo** – Frente de Loja, Fundo de Loja, Comunicação Corporativa, Treinamento

> [!NOTE]
> Os canais não devem ser considerados como um limite de segurança. Eles são um meio de organizar os trabalhadores para fins de colaboração.

*Discussão de prática recomendada*: ao projetar a estrutura de canais, é importante manter as coisas simples, especialmente quando se pretende integrar um grande número de usuários. Resista ao impulso de criar canais para cada situação, função ou tópico, a fim de minimizar a necessidade de treinamento. Para começar, escolha de três a cinco canais no máximo. Canais adicionais podem ser facilmente criados conforme a necessidade. Na verdade, por enquanto não há problema em usar apenas o canal geral!

#### <a name="steps-to-create-channels-for-teams"></a>Etapas para criar canais para as equipes

1. Localize o arquivo **TeamsChannels.csv** nos ativos de arquivo .zip.
1. Atualize o arquivo **TeamsChannels.csv** com as informações específicas da sua organização. Lembre-se das nossas melhores práticas acima.
1. Localize o script **CreateTeamsChannels.ps1** nos ativos de arquivo .zip.
1. No PowerShell, execute o script **TeamsChannels.ps1**.

## <a name="create-teams-policies"></a>Criar políticas do Teams

Como administrador, você pode usar as políticas de equipes no Microsoft Teams para controlar o que os usuários em sua organização podem ver. Por exemplo, você pode controlar quais aplicativos estão fixados na barra esquerda da área de trabalho ou do navegador da Web, ou a barra inferior em dispositivos móveis, a fim de simplificar a experiência do usuário final ao integrar uma grande quantidade de usuários. Algumas dessas políticas podem ser criadas com o PowerShell, e outras têm de ser criadas manualmente no console de administração do Teams.

*Discussão de prática recomendada*: para cada uma das seguintes políticas, optamos por criar realmente duas políticas: uma para os trabalhadores da linha de frente e outra para os gerentes da linha de frente. Você pode optar por criar quantos forem necessários. Para a maioria dos clientes, duas é uma quantidade boa para começar, mesmo que você atribua as mesmas configurações para cada grupo inicialmente. À medida que sua experiência com o Teams aumentar, você poderá optar por diferenciar ainda mais sua experiência e ter as duas políticas separadas já criadas, poderá tornar isso mais simples.

### <a name="create-teams-message-policies"></a>Criar políticas de mensagens do Teams

As políticas de mensagens são usadas para controlar quais recursos de mensagens de chat e canal estão disponíveis para usuários no Microsoft Teams.

*Discussão de prática recomendada*: embora seja possível usar a política global padrão criada automaticamente, optamos por criar uma política personalizada usando as etapas a seguir para fornecer uma experiência mais bloqueada, simples e diferenciada para os gerentes e trabalhadores da linha de frente.

#### <a name="steps-to-create-teams-message-policies"></a>Etapas para criar políticas de mensagens do Teams

1. Localize o arquivo **TeamsMessagingPolicies.csv** nos ativos de arquivo .zip.
1. Atualize o arquivo **TeamsMessagingPolicies.csv** com as informações específicas da sua organização. Informações adicionais sobre algumas das várias opções podem ser encontradas [aqui](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).
1. Localize o script **CreateTeamsMessagePolicies.ps1** nos ativos.
1. No PowerShell, execute o script **TeamsMessagePolicies.ps1**.

### <a name="create-teams-app-setup-policies"></a>Criar políticas de configuração de aplicativos do Teams

Como administrador, é possível usar as políticas de configuração de aplicativos para fazer o seguinte:

- Personalize o Teams para destacar os aplicativos mais importantes para os usuários. Você escolhe os aplicativos a serem fixados e define a ordem em que eles aparecem. A fixação de aplicativos permite mostrar os aplicativos que os usuários da sua organização precisam, inclusive aqueles criados por terceiros ou por desenvolvedores da sua organização.
- Controle se os usuários podem fixar aplicativos no Teams.

Os aplicativos do são fixados na barra do aplicativo. Esta é a barra do lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).

|Cliente da área de trabalho do Teams  |         |Cliente móvel do Teams  |
|---------|---------|---------|
|![Uma captura de tela do cliente da área de trabalho do Teams com aplicativos fixados na barra *app*.](media/FLW-Teams-Desktop-Client.png)         |         |![Uma captura de tela do cliente da área de trabalho do Teams com aplicativos fixados na barra *inferior*.](media/FLW-Teams-Mobile-Client.png) |

*Discussão de prática recomendada*: gerencie as políticas de configuração de aplicativos no centro administrativo do Microsoft Teams. Eles não podem ser criados com o PowerShell. Você pode usar a política global (padrão para toda a organização) ou criar políticas personalizadas e atribuí-las aos usuários. Os usuários em sua organização terão automaticamente a política global atribuída, a menos que você crie e atribua uma política personalizada. Para nossos propósitos, criaremos duas novas políticas para os trabalhadores e gerentes da linha de frente, a fim de proporcioná-los uma experiência mais simples e aperfeiçoada, facilitando a integração de um grande número de usuários simultaneamente. Você pode optar por personalizar a experiência conforme as necessidades da empresa.

#### <a name="create-the-firstline-manager-app-setup-policy"></a>Criar a política de configuração do aplicativo de gerente da linha de frente

As seguintes configurações podem ser personalizadas para atender às suas necessidades de negócios. Escolhemos algumas das opções recomendadas com base nas práticas recomendadas e para melhorar a facilidade de integrar novos usuários em escala. Para saber mais, clique [aqui](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para  **Aplicativos do Teams** > **Políticas de configuração**.
2. Clique em  **Adicionar**.  
3. Insira um nome e uma descrição para a política. Como exemplo: **Políticas de Configuração do Aplicativo de Gerente da Linha de Frente**.
![Imagem da política de configuração do aplicativo de gerente da linha de frente](media/FLW-FLM-App-Setup-Policy.png)

4. Desativar o **Carregamento de aplicativos personalizados**.
5. Desativar a **Permissão de fixação do usuário**.
![Permitir que o usuário fixe a alternância de imagem](media/FLW-Allow-User-Pinning.png).

6. Se ainda não estiver listado, adicione o aplicativo **Turnos**. Para saber mais sobre **Turnos**, clique [aqui](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md).
![Tela de adicionar aplicativos fixados, mostrando o aplicativo Turnos listado ao lado do botão Adicionar.](media/FLW-Add-Pinned-Apps.png)

7. Remover chamadas, caso isso apareça. Observação: a remoção desse recurso não o desabilitará para o usuário, mas impedirá que ele apareça na barra do aplicativo para simplificar a experiência do usuário final.
8. Organize os aplicativos na seguinte ordem para ditar a ordem na barra de aplicativos do Teams e, em seguida, clique em  **Salvar**.
    1. Atividade
    1. Bate-papo
    1. Equipes
    1. Calendário
    1. Turnos ![Captura de tela da lista de aplicativos do gerente na ordem.](media/FLW-Manager-Pinned-Apps.png)

#### <a name="create-the-firstline-worker-app-setup-policy"></a>Criar a política de configuração do aplicativo de trabalhador da linha de frente

As seguintes configurações podem ser personalizadas para atender às suas necessidades de negócios. Escolhemos algumas das opções recomendadas com base nas práticas recomendadas e para melhorar a facilidade de integrar novos usuários em escala. Para saber mais, clique [aqui](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para  **Aplicativos do Teams** > **Políticas de configuração**.
2. Clique em  **Adicionar**.
3. Insira um nome e uma descrição para a política. Como exemplo: **Políticas de Configuração do Aplicativo de Trabalhador da Linha de Frente**.
![Imagem da política de configuração do aplicativo de trabalhador da linha de frente](media/FLW-FLW-App-Setup-Policy.png)

4. Desativar o **Carregamento de aplicativos personalizados**.
5. Desativar a **Permissão de fixação do usuário**.
![Permitir que o usuário fixe a alternância de imagem](media/FLW-Allow-User-Pinning.png).

6. Se ainda não estiver listado, adicione o aplicativo **Turnos**. Para saber mais sobre **Turnos**, clique aqui.
![Tela de adicionar aplicativos fixados, mostrando o aplicativo Turnos listado ao lado do botão Adicionar.](media/FLW-Add-Pinned-Apps.png)

7. Remova reuniões e chamadas, caso apareçam. Observação: a remoção desses recursos não os desabilitará para o usuário, mas impedirá que eles apareçam na barra do aplicativo para simplificar a experiência do usuário final.
8. Organize os aplicativos na seguinte ordem para ditar a ordem na barra de aplicativos do Teams e, em seguida, clique em  **Salvar**.
    1. Atividade
    1. Bate-papo
    1. Teams
    1. Turnos ![Captura de tela da lista de aplicativos do trabalhador na ordem.](media/FLW-Worker-Pinned-Apps.png)

### <a name="create-app-permission-policies"></a>Criar políticas de permissão de aplicativos

Como administrador, você pode usar as políticas de permissão do aplicativo para controlar quais aplicativos estarão disponíveis para os usuários do Microsoft Teams em sua organização. Você pode permitir ou bloquear todos os aplicativos, ou aplicativos específicos publicados pela Microsoft, por terceiros e pela sua organização. Ao bloquear um aplicativo, os usuários que têm a política não conseguem instalá-lo da loja de aplicativos do Teams. Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.

*Discussão de prática recomendada*: gerencie as políticas de configuração de aplicativos no centro administrativo do Microsoft Teams. Eles não podem ser criados com o PowerShell. Você pode usar a política global (padrão para toda a organização) ou criar políticas personalizadas e atribuí-las aos usuários. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Para nossos propósitos, criaremos duas novas políticas para os trabalhadores e gerentes da linha de frente, a fim de proporcionar uma experiência mais simples e aperfeiçoada, facilitando a integração de um grande número de usuários simultaneamente. Claro que você pode optar por personalizar a experiência conforme as necessidades da empresa.

#### <a name="create-the-firstline-manager-app-permission-policy"></a>Criar a política de permissão do aplicativo de gerente da linha de frente

As seguintes configurações podem ser personalizadas para atender às suas necessidades de negócios. Estas são algumas das opções com base nas práticas recomendadas que podem melhorar a facilidade de integração de novos usuários em escala. Para saber mais, clique [aqui](teams-app-permission-policies.md).

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para  **Aplicativos do Teams** > **Políticas de permissão**.
2. Clique em  **Adicionar**.
![Mostra a página de adicionar política de permissão para aplicativos, com seções para aplicativos da Microsoft, de terceiros e de locatários.](media/FLW-add-app-permission-policy.png)

3. Insira um nome e uma descrição para a política. Como exemplo: Política de Permissão do Aplicativo de Gerente da Linha de Frente.
4. Em aplicativos da Microsoft, escolha **Permitir todos os aplicativos**.
5. Em aplicativos de terceiros, escolha **Permitir todos os aplicativos**.
6. Em aplicativos do locatário, escolha **Permitir todos os aplicativos**.
7. Clique em **Salvar**.

#### <a name="create-the-firstline-worker-app-permission-policy"></a>Criar a política de permissão do aplicativo de trabalhador da linha de frente

As seguintes configurações podem ser personalizadas para atender às suas necessidades de negócios. Estas são algumas das opções com base nas práticas recomendadas que podem melhorar a facilidade de integração de novos usuários em escala. Para saber mais, clique [aqui](teams-app-permission-policies.md).

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para  **Aplicativos do Teams** > **Políticas de permissão**.
2. Clique em  **Adicionar**.
![Mostra a página de adicionar política de permissão para aplicativos, com seções para aplicativos da Microsoft, de terceiros e de locatários.](media/FLW-add-app-permission-policy.png)

3. Insira um nome e uma descrição para a política. Como exemplo: Política de Permissão do Aplicativo de Trabalhador da Linha de Frente.
4. Em aplicativos da Microsoft, escolha **Permitir todos os aplicativos**.
5. Em aplicativos de terceiros, escolha **Bloquear todos os aplicativos**.
6. Em aplicativos do locatário, escolha **Permitir todos os aplicativos**.
7. Clique em **Salvar**.

## <a name="create-and-set-up-users"></a>Criar e configurar usuários

### <a name="create-user-and-security-groups"></a>Criar usuário e grupos de segurança

Para trabalhar com uma grande quantidade de usuários no Teams, primeiro é necessário ter os usuários criados no Azure AD. Há muitas maneiras de provisionar um grande número de usuários, mas vamos destacar o seguinte:

- Se esses usuários já existirem em um dos seguintes sistemas de RH, use os links a seguir para configurar o provisionamento do usuário:
  - Fatores de Sucesso SAP – [Tutorial: configurar o SAP SuccessFactors para o provisionamento de usuários do Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).
  - Dia útil – [Tutorial: configurar o dia útil para o provisionamento automático do usuário](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).
- Caso tenha suas informações de usuário em outros sistemas, prossiga com as seguintes etapas.

A fim de gerenciar esses usuários em escala com mais eficiência, você precisa criar dois grupos de segurança para os trabalhadores da linha de frente e os gerentes da linha de frente, e provisionar esses usuários diretamente para os grupos de segurança, seguindo essas etapas:

1. Localize o arquivo **SecurityGroups.csv** nos ativos de arquivo .zip.
1. Atualize o arquivo **SecurityGroups.csv** com as informações específicas da organização.
    1. Certifique-se de atualizar os campos **MessagePolicy**, **AppPermissionPolicy** e **AppSetupPolicy** para mapear as políticas adequadas que você criou anteriormente.
    1. Certifique-se de atualizar o campo **LicensePlan** para refletir o licenciamento que você pretende dar a cada um desses usuários. Para mais informações sobre nomes de produtos e identificadores de planos de serviços, confira a documentação [aqui](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
1. Localize o arquivo **Users.csv** nos ativos de arquivo .zip.
1. Atualize o arquivo **Users.csv** com as informações específicas da organização.
    1. Por padrão, o script fornecido criará um usuário com uma senha temporária que deve ser alterada no primeiro logon. Se você não quiser usar a senha padrão, edite o script **CreateUsers.ps1** para atender às suas necessidades.
    1. Certifique-se de atualizar o campo SecurityGroup para refletir o nome apropriado criado anteriormente.
1. No PowerShell, execute o script **CreateUsers.ps1** de ativos.

### <a name="assign-licensing-to-users-by-group-based-licensing"></a>Atribuir licenciamento a usuários por licenciamento com base em grupo

Os serviços de nuvem pagos da Microsoft, como o Office 365, Enterprise Mobility + Security, Dynamics 365 e outros produtos similares, exigem licenças. Estas licenças são atribuídas a cada usuário que necessita ter acesso a esses serviços. Para gerencias as licenças, os administradores usam um dos portais de gerenciamento (Office ou Azure) e cmdlets do PowerShell. O Azure Active Directory (Azure AD) é a infraestrutura subjacente que oferece suporte ao gerenciamento de identidade para todos os serviços de nuvem da Microsoft. O Azure AD armazena informações sobre os estados de atribuição de licenças para os usuários.

A fim de permitir o licenciamento em escala, o Azure AD inclui agora o licenciamento baseado em grupos, e por esta razão criamos os grupos de segurança no início deste artigo. Você pode atribuir uma ou mais licenças de produto a um grupo. O Azure AD garante que as licenças sejam atribuídas a todos os membros do grupo. Todos os novos membros que ingressarem no grupo receberão as licenças apropriadas. As licenças são removidas dos membros que deixam o grupo. Este gerenciamento de licenciamento elimina a necessidade de automatizar gerenciamentos via PowerShell para refletir as mudanças na organização e estrutura departamental por usuário.

## <a name="assign-users-and-policies"></a>Atribuir usuários e políticas

### <a name="assigning-users-to-teams"></a>Atribuindo usuários às equipes

Agora que você criou os usuários e criou as equipes, é hora de colocar todos os usuários nas equipes apropriadas.

1. Encontre o arquivo **Users.csv** nos ativos de arquivo .zip e certifique-se de ter um mapeamento exato para as equipes desse arquivo.
1. No PowerShell, execute o script **AssignUserstoTeams.ps1** dos ativos de arquivo .zip.

### <a name="assign-teams-policies-to-users"></a>Atribuir políticas de equipes aos usuários

Agora que você criou os usuários e as políticas para modificar sua experiência nas equipes, é hora de atribuir essas políticas aos usuários corretos.

1. Encontre o arquivo **SecurityGroups.csv** nos ativos de arquivo .zip e certifique-se de ter um mapeamento exato das políticas para os grupos.
1. No PowerShell, execute o script **AssignPoliciestoUsers.ps1** dos ativos de arquivo .zip.

## <a name="test-and-validate"></a>Testar e validar

### <a name="check-for-errors"></a>Verificar se há erros

A medida que os scripts anteriores foram executados, erros ou exceções foram gravados em um arquivo .csv localizado na pasta de logs dos ativos de arquivo .zip. Esse arquivo pode ser usado para investigar todos os problemas que possam ter ocorrido.

Um exemplo de exceção poderia ser se você tentasse criar uma equipe que já existisse no seu locatário.

1. Encontre a pasta **Logs** e revise qualquer arquivo .csv que ela possa conter. Se não houver exceções, poderá não encontrar um arquivo de exceção aqui.

### <a name="login-to-teams-with-a-test-user"></a>Entrar no Teams com um usuário de teste

Agora que você completou todas as etapas, é hora de verificar o trabalho concluído.

1. Escolha um usuário da sua lista anterior e entre no Teams com as credenciais desse usuário.
1. Verifique se a aparência do Teams é a esperada. Caso contrário, reveja as seções **Criar políticas do Teams** e **Atribuir políticas do Teams aos usuários**.
1. Verifique se o usuário está na equipe correta. Caso contrário, reveja as seções **Criar e configurar usuários** e **Atribuir usuários ao Teams**.
