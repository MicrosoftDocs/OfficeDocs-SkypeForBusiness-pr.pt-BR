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
ms.openlocfilehash: 7a57de3528ac9ef0f950c7034b3c6ee3860b53ea
ms.sourcegitcommit: ad82786076cc965e75b1ec5ffd4bc9bf75437340
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45028167"
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

Baixe os ativos a partir [deste local](https://aka.ms/flwteamsscale).

> [!IMPORTANT]
> Os scripts no link acima são fornecidos como estão pela Microsoft, e devem ser modificados para suas necessidades individuais.

## <a name="technical-requirements"></a>Requisitos técnicos

- O locatário deve ter o número adequado de licenças disponíveis que incluam o Microsoft Teams. Se você ainda não possui essas licenças, consulte o [Exploratório do Teams](teams-exploratory.md) para obter uma assinatura de avaliação gratuita.
- O usuário que executa estas etapas deve ter as seguintes funções atribuídas: Administrador Global, Administrador de Usuários e Administrador de Serviço do Teams, no Microsoft Azure Active Directory.
- Os usuários devem ter direitos para instalar e configurar softwares no computador local.

## <a name="step-by-step-process-overview"></a>Processo passo a passo

1. **Configure seu ambiente**
    1. Download do repositório GitHub contendo os scripts e documentação de exemplo do Windows PowerShell
    1. Configurar o ambiente local
    1. Credenciais de configuração
    1. Configurar Módulos do Windows PowerShell e variáveis ambientais
1. **Criar e configurar equipes**
    1. Criar equipes
    1. Etapas para a criação de equipes
    1. Criar canais para as equipes
1. **Criar Políticas do Teams**
    1. Criar políticas de mensagens do Teams
    1. Criar políticas de configuração de aplicativos do Teams
    1. Criar políticas de permissão de aplicativos do Teams
1. **Usuários e grupos de segurança**
    1. Criar usuários e grupos de segurança
    1. Atribuir licenciamento a usuários por meio de um licenciamento com base em grupo
1. **Atribuir Usuários e Políticas**
    1. Atribuir usuários ao Teams
    1. Atribuir políticas do Teams aos usuários
    1. OPCIONAL: converter tipo de associação do grupo
1. **Testar e validar**
    1. Entrar no Teams com um usuário de teste
    1. Verificar se há erros
    1. Tratamento de erros
1. **Leituras adicionais**

## <a name="set-up-your-environment"></a>Configurar ambiente

As etapas a seguir permitem configurar o ambiente:

### <a name="download-from-the-github-repository-containing-sample-powershell-scripts-and-documentation"></a>Download do repositório GitHub contendo exemplos de scripts e documentação do Windows PowerShell

Antes de prosseguir, será necessário baixar os scripts [deste local](https://aka.ms/flwteamsscale).

### <a name="configure-the-local-environment"></a>Configurar o ambiente local

A configuração das variáveis de ambiente local permite que os scripts mencionados aqui sejam executados usando caminhos relativos. O rootPath é a raiz de onde você clonou este repositório, e o tenantName está no formato **yourTenant.onmicrosoft.com** (https não deve ser incluído).

1. Abra uma sessão do Windows PowerShell e navegue até a pasta scripts dentro do repositório git clonado.
1. Execute o script .\SetConfig.ps1 -tenantName [nome do seu locatário] -rootPath "caminho completo para a raiz do repositório git".

Por exemplo: .\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"

### <a name="setup-credentials"></a>Credenciais de configuração

> [!IMPORTANT]
> A forma como as credenciais são gerenciadas nesses scripts pode não ser adequada para o seu uso; ela pode ser facilmente alterada para atender aos seus requisitos. Sempre siga os padrões e práticas da sua empresa para proteger contas de serviço e identidades gerenciadas.

Os scripts usam credenciais armazenadas como arquivos XML em $ENV:LOCALAPPDATA\keys, ou seja, a pasta AppData\Local. A função auxiliar **Set-Creds** no módulo **BulkAddFunctions.psm1** precisa ser chamada para definir as credenciais usadas para executar esses scripts. Esta técnica elimina a necessidade de autenticação em todos os pontos de extremidade de serviço, mantendo as credenciais em um armazenamento local. De dentro de cada script, as credenciais apropriadas são lidas com a função auxiliar **Get-Creds**, e essas credenciais são usadas para conectar-se aos vários serviços.

Quando você chama **Set-Creds**, é solicitado que você forneça um nome de arquivo XML que será gravado em $ENV:LOCALAPPDATA\keys. Você pode ter diferentes credenciais para diferentes serviços. Por exemplo, você pode ter diferentes credenciais para MicrosoftTeams, AzureAD e MSonline; nesse caso, você pode executar **Set-Creds** mais de uma vez, salvando cada arquivo de credencial com seu próprio nome significativo.

Exemplos: Set-Creds msol-cred.xml Set-Creds azuread-cred.xml Set-Creds teams-cred.xml

Execute o script **SetCreds.ps1** para salvar suas credenciais. Você verá uma solicitação "Executando a Operação" Export-Clixml "..."; digite 'Y' para aprovar.

> [!NOTE]
> A conta usada para as credenciais não pode exigir MFA (autenticação multifator).

Aqui está um exemplo de como os vários scripts usam as credenciais salvas para autenticar:

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = Get-Creds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

### <a name="configure-powershell-modules-and-environmental-variables"></a>Configurar os módulos do Windows PowerShell e as variáveis de ambiente

Você precisará instalar e conectar-se a vários módulos do Windows PowerShell, incluindo Microsoft Azure Active Directory, MSAL, MSCloudUtils e MicrosoftTeams.

1. Localize o **ConfigurePowerShellModules.ps1** na pasta de scripts no repositório.
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

1. Localize o arquivo **TeamsInformation.csv** na pasta de dados no repositório.
1. Atualize as informações no arquivo **TeamsInformation.csv** com as informações específicas da sua organização. Lembre-se das nossas melhores práticas acima.
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

1. Localize o arquivo **TeamsChannels.csv** na pasta de scripts no repositório.
1. Atualize o arquivo **TeamsChannels.csv** com as informações específicas da sua organização. Lembre-se das nossas melhores práticas acima.
1. Localize o script **CreateTeamsChannels.ps1** na pasta de scripts no repositório.
1. No Windows PowerShell, execute o script **CreateTeamsChannels.ps1**.

## <a name="create-teams-policies"></a>Criar políticas do Teams

Como administrador, você pode usar as políticas de equipes no Microsoft Teams para controlar o que os usuários em sua organização podem ver. Por exemplo, você pode controlar quais aplicativos estão fixados na barra esquerda da área de trabalho ou do navegador da Web, ou a barra inferior em dispositivos móveis, a fim de simplificar a experiência do usuário final ao integrar uma grande quantidade de usuários. Algumas dessas políticas podem ser criadas com o PowerShell, e outras têm de ser criadas manualmente no console de administração do Teams.

*Discussão de prática recomendada*: para cada uma das seguintes políticas, optamos por criar realmente duas políticas: uma para os trabalhadores da linha de frente e outra para os gerentes da linha de frente. Você pode optar por criar quantos forem necessários. Para a maioria dos clientes, duas é uma quantidade boa para começar, mesmo que você atribua as mesmas configurações para cada grupo inicialmente. À medida que sua experiência com o Teams aumentar, você poderá optar por diferenciar ainda mais sua experiência e ter as duas políticas separadas já criadas, poderá tornar isso mais simples.

### <a name="create-teams-message-policies"></a>Criar políticas de mensagens do Teams

As políticas de mensagens são usadas para controlar quais recursos de mensagens de chat e canal estão disponíveis para usuários no Microsoft Teams.

*Discussão de prática recomendada*: embora seja possível usar a política global padrão criada automaticamente, optamos por criar uma política personalizada usando as etapas a seguir para fornecer uma experiência mais bloqueada, simples e diferenciada para os gerentes e trabalhadores da linha de frente.

#### <a name="steps-to-create-teams-message-policies"></a>Etapas para criar políticas de mensagens do Teams

1. Localize o arquivo **TeamsMessagingPolicies.csv** na pasta de scripts no repositório.
1. Atualize o arquivo **TeamsMessagingPolicies.csv** com as informações específicas da sua organização. Informações adicionais sobre algumas das várias opções podem ser encontradas [aqui](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).
1. Localize o script **CreateTeamsMessagePolicies.ps1** na pasta de scripts no repositório.
1. No Windows PowerShell, execute o script **CreateTeamsMessagePolicies.ps1**.

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

### <a name="create-teams-app-permission-policies"></a>Criar políticas de permissão de aplicativos do Teams

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

## <a name="users-and-security-groups"></a>Usuários e grupos de segurança

### <a name="create-users-and-security-groups"></a>Criar usuários e grupos de segurança

Para trabalhar com uma grande quantidade de usuários no Teams, primeiro é necessário ter os usuários criados no Azure AD. Há muitas maneiras de provisionar um grande número de usuários, mas vamos destacar o seguinte:

- Se esses usuários já existirem em um dos seguintes sistemas de RH, use os links a seguir para configurar o provisionamento do usuário:
  - Fatores de Sucesso SAP – [Tutorial: configurar o SAP SuccessFactors para o provisionamento de usuários do Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).
  - Dia útil – [Tutorial: configurar o dia útil para o provisionamento automático do usuário](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).
- Caso tenha suas informações de usuário em outros sistemas, prossiga com as seguintes etapas.

A fim de gerenciar esses usuários em escala com mais eficiência, você precisa criar dois grupos de segurança para os trabalhadores da linha de frente e os gerentes da linha de frente, e provisionar esses usuários diretamente para os grupos de segurança, seguindo essas etapas:

1. Localize o arquivo **Users.csv** na pasta de scripts no repositório.
1. Atualize o arquivo **Users.csv** com as informações específicas da organização.
    1. Por padrão, o script fornecido criará um usuário com uma senha temporária que deve ser alterada no primeiro logon. Se você não quiser usar a senha padrão, edite o script **CreateUsers.ps1** para atender às suas necessidades.
    1. Certifique-se de atualizar o campo SecurityGroup para refletir o nome apropriado criado anteriormente.
1. Localize o arquivo **SecurityGroups.csv** na pasta de scripts no repositório.
1. Atualize o arquivo **SecurityGroups.csv** com as informações específicas do grupo de segurança da sua organização.
    1. Certifique-se de atualizar os campos **MessagePolicy**, **AppPermissionPolicy** e **AppSetupPolicy** para mapear as políticas adequadas que você criou anteriormente.
    1. Certifique-se de atualizar o campo **LicensePlan** para refletir o licenciamento que você pretende dar a cada um desses usuários. Para mais informações sobre nomes de produtos e identificadores de planos de serviços, confira a documentação [aqui](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
1. No Windows PowerShell, execute o script **CreateUsers.ps1** de ativos.

### <a name="assign-licensing-to-users-via-group-based-licensing"></a>Atribuir licenciamento a usuários por meio de um licenciamento com base em grupo

Os serviços de nuvem pagos da Microsoft, como o Microsoft 365, Office 365, Enterprise Mobility + Security, Dynamics 365 e outros produtos similares, exigem licenças. Estas licenças são atribuídas a cada usuário que necessita ter acesso a esses serviços. Para gerencias as licenças, os administradores usam um dos portais de gerenciamento (Office ou Azure) e cmdlets do PowerShell. O Azure Active Directory (Azure AD) é a infraestrutura subjacente que oferece suporte ao gerenciamento de identidade para todos os serviços de nuvem da Microsoft. O Azure AD armazena informações sobre os estados de atribuição de licenças para os usuários.

A fim de permitir o licenciamento em escala, o Azure AD inclui agora o licenciamento baseado em grupos, e por esta razão criamos os grupos de segurança no início deste artigo. Você pode atribuir uma ou mais licenças de produto a um grupo. O Azure AD garante que as licenças sejam atribuídas a todos os membros do grupo. Todos os novos membros que ingressarem no grupo receberão as licenças apropriadas. As licenças são removidas dos membros que deixam o grupo. Este gerenciamento de licenciamento elimina a necessidade de automatizar gerenciamentos via PowerShell para refletir as mudanças na organização e estrutura departamental por usuário.

## <a name="assign-users-and-policies"></a>Atribuir usuários e políticas

### <a name="assign-users-to-teams"></a>Atribuir usuários a equipes

Agora que você criou os usuários e as equipes, é hora de colocar todos os usuários nas equipes apropriadas.

1. Localize o arquivo **Users.csv** na pasta de dados no repositório e certifique-se de que você tenha um mapeamento exato para as equipes neste arquivo.
1. No Windows PowerShell, execute o script **AssignUserstoTeams.ps1** na pasta de scripts no repositório.

### <a name="assign-teams-policies-to-users"></a>Atribuir políticas de equipes aos usuários

Agora que você criou os usuários e as políticas para modificar sua experiência nas equipes, é hora de atribuir essas políticas aos usuários corretos.

1. Localize o arquivo **SecurityGroups.csv** na pasta de dados no repositório e certifique-se de que você tenha um mapeamento preciso das políticas para os grupos.
1. No Windows PowerShell, execute o script **AssignPoliciestoUsers.ps1** na pasta de scripts no repositório.

### <a name="optional-convert-group-membership-type"></a>OPCIONAL: converter tipo de associação do grupo

> [!NOTE]
> Esta etapa é para pessoas que tenham o Microsoft Azure Active Directory P1 ou superior.

Quando licenciado para o Microsoft Azure Active Directory P1 ou superior, você tem a opção de usar a Associação Dinâmica de Grupo em vez de usar a associação atribuída. Os scripts que criaram as equipes também criaram grupos do Office do tipo de associação Atribuído, o que significa que seus membros devem ser adicionados explicitamente.

Usando a Associação Dinâmica, regras são escritas para determinar se alguém é membro da equipe ou não.

> [!NOTE]
> Quando você executar este script, os membros atuais do grupo serão removidos (exceto seus proprietários) e novos membros serão adicionados quando o trabalho de sincronização da associação for executado.

1. Localize o arquivo **migrateGroups.csv** na pasta de dados no repositório.
1. Atualize o arquivo CSV **migrateGroups.csv** com os grupos que serão migrados, juntamente com a regra para associação dinâmica.
1. Localize o arquivo **ConvertGroupMembershipType.ps1** na pasta de scripts no repositório.
1. No Windows PowerShell, execute o script **ConvertGroupMembershipType.ps1**

## <a name="test-and-validate"></a>Testar e validar

### <a name="login-to-teams-with-a-test-user"></a>Entrar no Teams com um usuário de teste

Agora que você completou todas as etapas, é hora de verificar o trabalho concluído.

1. O usuário criado terá uma senha inicial, que está no arquivo CreateUsers.ps1, e precisará alterá-la na primeira vez que entrar.
1. Verifique se a aparência do Teams é a esperada. Caso contrário, reveja as seções **Criar políticas do Teams** e **Atribuir políticas do Teams aos usuários**.
1. Verifique se o usuário está na equipe correta. Caso contrário, reveja as seções **Criar e configurar usuários** e **Atribuir usuários ao Teams**.

> [!NOTE]
> Se o provisionamento de funcionários de contato direto for gerenciado por meio da sua equipe de Gerenciamento de Acesso, você precisará seguir o processo da equipe para fornecer as credenciais ao funcionário.

### <a name="check-for-errors"></a>Verificar se há erros

Enquanto você executava os scripts anteriores, erros ou exceções foram gravados em um arquivo .csv localizado na pasta de logs na sua cópia do repositório. Esse arquivo pode ser usado para investigar todos os problemas que possam ter ocorrido.

Um exemplo de exceção poderia ser se você tentasse criar uma equipe que já existisse no seu locatário.

1. Encontre a pasta **Logs** e revise qualquer arquivo .csv que ela possa conter. Se não houver exceções, poderá não encontrar um arquivo de exceção aqui.

### <a name="error-handling"></a>Tratamento de erros

O tratamento mínimo de erros foi implementado nesses scripts de exemplo.  Existem blocos try/catch e, se acionados, armazenamos o erro em uma variável no bloco catch. O tratamento de erros adicional deve ser implementado de acordo com suas preferências.

## <a name="further-reading"></a>Leituras adicionais

- [Novo canal de equipe (Windows PowerShell)](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps)
- [Nova política de mensagens do Teams (Windows PowerShell)](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)
- [Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module)
- [Atribuir licenças e contas de usuário usando o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
