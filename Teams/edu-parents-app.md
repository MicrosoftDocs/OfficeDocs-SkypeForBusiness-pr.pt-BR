---
title: Administração instalação de Pais em Teams para Educação
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Artigo do Microsoft Teams documentando pré-requisitos e instalação de Pais em Teams para Educação.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- admindeeplinkTEAMS
appliesto:
- Microsoft Teams
ms.openlocfilehash: f2d0d916028a026d7706fd317ba25d16af213a81
ms.sourcegitcommit: 55d2f515f5040b4c083f529d7b818c84d42378a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2022
ms.locfileid: "69147478"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurar a conexão pai no Microsoft Teams para Educação

A Conexão Pai em Teams para Educação ajuda os educadores a se conectarem e se envolverem com os pais e responsáveis dos alunos em suas equipes de classe usando o Teams.

Este artigo fornece diretrizes para os profissionais de TI de educação sobre os requisitos e a configuração da Conexão Pai.

## <a name="share-guardian-and-educator-resources"></a>Compartilhar recursos de tutor e educador

Aqui estão alguns recursos que os administradores de TI podem compartilhar com guardiões e educadores sobre como eles podem começar a usar a Conexão Pai.

- Para obter diretrizes sobre como configurar os guardiões, consulte [Conectar-se com educadores no Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).
- Para obter diretrizes sobre como configurar educadores, consulte [Comunicar-se com os responsáveis no Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

## <a name="benefits-of-parent-connection"></a>Benefícios da conexão pai

A Conexão de Pais permite que educadores e responsáveis conversem, enviem email e chamem usando o Teams.

- Os educadores podem iniciar chats com os responsáveis.
  - Se o responsável não tiver uma conta de consumidor do Teams ou ainda não tiver ingressado no Teams, ele receberá a mensagem do educador junto com um convite por email para ir ao Teams. Isso só se aplica nos casos em que os limites de convite não foram atingidos, e o chat é um novo chat ou um chat existente que foi reentrado da Conexão Pai.
- Ele funciona com chat supervisionado. Para obter mais informações, consulte [Usar chats supervisionados no Microsoft Teams](supervise-chats-edu.md).
  - Por padrão, os guardiões têm permissões restritas, portanto, não podem conversar com os alunos ou remover usuários de chats.
  - Essa configuração pode ser alterada pelo administrador do locatário.
- Os educadores podem selecionar um email do guardião para enviar um email usando seu cliente de email nativo.
- Os educadores podem selecionar o número de telefone de um guardião para chamá-los no Teams.

> [!IMPORTANT]
> Para clicar em chamar a funcionalidade no Teams, seu locatário precisa:
>
> - Recursos do PBX (Public Branch Exchange).
> - Conexão com o PSTN.
>
> Microsoft 365 A1 e planos A3 não incluem recursos PBX nem conexão PSTN. Você pode comprar [licenças de complemento para cada uma delas](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
>
> Microsoft 365 A5 planos incluem apenas recursos PBX usando o Teams Phone System. Você ainda precisará [comprar um Plano de Chamada do Teams ou usar uma solução de terceiros](pstn-connectivity.md) para se conectar a números externos no PSTN.
>
> Para obter mais informações sobre todas as opções para obter conectividade PSTN, confira [Opções de conectividade PSTN](pstn-connectivity.md).
>
> Para obter mais informações sobre o licenciamento de chamadas do Teams, consulte [Opções de licenciamento de complemento do Teams](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

## <a name="requirements"></a>Requisitos

Você precisa usar o Microsoft Graph ou o SDS (School Data Sync) para preencher as informações de contato relacionadas aos pais e responsáveis de cada aluno.

### <a name="graph-api"></a>API do Graph

Se você já usar o [SDK do Microsoft Graph PowerShell](/powershell/microsoftgraph/overview) para criar identidades de estudante, poderá incluir facilmente [o tipo de recurso relatedContact](/graph/api/resources/relatedcontact).

### <a name="school-data-sync"></a>Sincronização de dados escolares

Os dados de contato do guardião do Teams permanecem atualizados com o SIS usando o SDS (Sincronização de Dados Escolares), quando o SDS é configurado para sincronizar regularmente.

Se o guardião for removido dos registros *de um aluno* , todos os chats existentes envolvendo eles conterão uma faixa visível para o proprietário do chat. Essa faixa conscientizará o proprietário do chat sobre a alteração, solicitando que eles removam o guardião do chat. A Microsoft não atualizará automaticamente a associação de chat para remover o guardião.

- Você precisa de SDS (Sincronização de Dados Escolares) para preencher as informações de **contato relacionadas aos** pais e responsáveis de cada aluno.
  - [Implantar SDS](/schooldatasync/parents-and-guardians-in-sds)

- Se você precisar de ajuda para configurar o SDS e preencher **contatos relacionados aos** pais e responsáveis para os alunos em seu locatário, entre em contato com a equipe de Sucesso do Cliente da EDU por:
  - Concluindo o processo de RFA no [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrindo um tíquete no [Suporte](https://aka.ms/sdssupport).

- Atualmente, o SDS só dá suporte à ingestão de dados baseada em CSV para contatos pai; no entanto, você pode usar [a Sincronização de API do PowerSchool](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) ou [a Sincronização de API do OneRoster](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) para todos os dados de lista e apenas adicionar contatos pai usando CSV.
  - Crie um segundo perfil de sincronização usando o [formato CSV do SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds) ou [o formato CSV do SDS v2.1](/schooldatasync/sds-v2.1-csv-file-format-classic).
  - Puxe os dois [arquivos Pai](/schooldatasync/parent-contact-sync-file-format) preenchidos com o restante dos arquivos v1/v2.1 vazios (apenas os cabeçalhos).
    - User.csv
    - Guardianrelationship.csv
      - O valor *da função* precisa ser concluído para que cada pai e responsável indique se eles são um `parent` ou `guardian`.
        - Somente os valores de `parent` ou `guardian` têm suporte no aplicativo. Outros valores resultarão em erros.
        - Para o formato SDS v1, ele será rotulado como **Role**, mas para o formato SDS v2.1, ele será rotulado como **relationshipRole**.
  - Para exibir um conjunto de exemplos dos arquivos CSV, consulte os [arquivos GitHub de Atributos Mínimos Necessários](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Se você quiser automatizar o pull nos arquivos CSV após a sincronização inicial, leia nosso [documento CSV Sincronização de Arquivos Automação](/schooldatasync/csv-file-sync-automation).
  - Para obter ajuda para configurar a sincronização de dados do SDS, entre em contato com [nossa equipe de sucesso do cliente](https://www.microsoft.com/fasttrack?rtc=1) ou [abra um tíquete de suporte](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center-policies"></a>Políticas de centro de administração do Teams

- Os proprietários da equipe de classe devem ter o chat do Teams ativado.
- Os proprietários de equipe de classe devem ter acesso externo com **contas do Teams não gerenciadas por uma organização** ativada.
  - Isso deve ser ativado no nível do locatário e no nível do usuário. A configuração no nível do locatário pode ser encontrada em **Usuários > Acesso Externo** no centro de administração do Teams. Essa configuração também pode ser acessada por meio do PowerShell. As políticas de acesso externo no nível do usuário só podem ser acessadas por meio do PowerShell. Para obter mais informações, confira os [comandos do PowerShell abaixo](#allow-external-access-with-teams-accounts-not-managed-by-an-organization).
- Para permitir a criação de reunião do aplicativo Conexão Pai, as seguintes políticas devem ser ativadas:
  - [Permitir agendamento de reunião privada](meeting-policies-in-teams.md#allow-scheduling-private-meetings).
  - [Permitir que usuários anônimos participem da reunião](meeting-policies-participants-and-guests.md#let-anonymous-people-join-a-meeting).

#### <a name="parent-and-guardian-restrictions"></a>Restrições de pais e responsáveis

Pais e responsáveis são classificados como *usuários externos* na Conexão de Pais, o que significa que eles não têm direitos completos de locatário. Eles só têm acesso ao chat ou chats dos quais fazem parte e os arquivos, imagens e outros conteúdos compartilhados no chat.

Para chats externos, usuários internos e externos podem adicionar usuários ao chat. Para saber mais sobre a experiência de chat externo, confira [Gerenciar reuniões externas e chat no Microsoft Teams](manage-external-access.md).

Além disso, usuários externos podem ver a presença (offline, disponível, ocupado etc.) dos usuários da sua organização, mas isso pode ser desativado usando o PowerShell para proteger a privacidade dos usuários. No PowerShell, use [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) e defina ``EnablePrivacyMode=true``.

Embora pais e responsáveis sejam usuários externos, suas contribuições para chats são detectáveis. Saiba como conduzir uma investigação de descoberta eletrônica do Teams lendo [Conduzir uma investigação de descoberta eletrônica do conteúdo no Microsoft Teams](ediscovery-investigation.md).

> [!IMPORTANT]
> Os administradores de TI devem educar todos os Proprietários de Classe sobre as melhores práticas para compartilhar informações dos alunos durante o chat, incluindo riscos à privacidade dos alunos.

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>Bloquear um pai ou responsável em um chat

Os educadores podem bloquear um guardião no chat iniciado na Conexão Pai.

O proprietário da classe pode:

1. Abra o cartão de perfil do guardião, selecione a reticência e **Bloquear Usuário**.
2. Em seguida, remova o guardião do chat.

O usuário bloqueado não poderá iniciar outros chats com o proprietário da classe.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Permitir acesso externo com contas do Teams não gerenciadas por uma organização

Para permitir que os educadores se comuniquem com pais e responsáveis no Teams, o administrador de TI do locatário de educação precisa atualizar as políticas do locatário para permitir acesso externo para contas do Teams fora do locatário. Para obter mais informações sobre como gerenciar o acesso externo, veja [Gerenciar acesso externo no Microsoft Teams](manage-external-access.md).

Aqui estão as etapas para ativar o acesso externo para pais e responsáveis.

1. Instale o módulo mais recente do Microsoft Teams PowerShell aqui [https://www.powershellgallery.com/packages/MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams).

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Usando credenciais com privilégios de administrador, execute os seguintes comandos:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    A configuração de política que ativa o acesso externo com contas do Teams não gerenciadas por uma organização no nível do usuário (`EnableTeamsConsumerAccess`) é ativada por padrão para todas as políticas de acesso externo no nível do usuário. Tanto a configuração no nível do locatário quanto a configuração de política no nível do usuário precisam ser ativadas para que um usuário tenha acesso externo com contas do Teams não gerenciadas por uma organização. Se você não quiser que todos os usuários do seu locatário tenham esse acesso ativado, verifique se a configuração no nível do locatário está desativada, atualize as políticas de acesso externo no nível do usuário atribuídas aos usuários e ative a configuração no nível do locatário.

    Para verificar quais políticas de acesso externo no nível do usuário existem e a quem elas estão atribuídas, você pode usar as seguintes etapas:

3. Verifique se existem políticas de acesso externo no nível do usuário.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Para cada política diferente da política 'Global', verifique quais usuários têm a política atribuída.

    > [!NOTE]
    > Todos os usuários que não tiverem uma política específica atribuída voltarão à política 'Global'. Todos os novos usuários adicionados ao locatário terão a política 'Global' atribuída.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Como todas as políticas de acesso externo no nível do usuário foram `EnableTeamsConsumerAccess` definidas como true por padrão, se você quiser ajustar a `EnableTeamsConsumerAccess` configuração para usuários específicos, você pode criar/modificar políticas de acesso externo existentes com configurações ajustadas e/ou reatribuir usuários para políticas novas ou existentes usando os seguintes cmdlets do PowerShell:

- Criar uma nova política de acesso externo: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizar uma política de acesso externo existente (incluindo a política 'Global'): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> As seguintes políticas padrão de assinatura não podem ser modificadas: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. A política 'FederationAndPICDefault' costumava ser atribuída a todos os usuários por padrão, no entanto, novos usuários agora recebem a política 'Global' por padrão. Se você precisar alterar as configurações de política para usuários que têm essas políticas padrão de assinatura atribuídas, atribua políticas diferentes com as configurações corretas a esses usuários.

- Atribuir uma política de acesso externo a um único usuário: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Atribuir uma política a um conjunto de [usuários: New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Depois que as políticas de acesso externo no nível do usuário forem definidas corretamente para os usuários em seu locatário, você poderá ativar a configuração no nível do locatário (`AllowTeamsConsumer`) para o locatário usando o seguinte cmdlet:

- Defina as configurações de federação para seu locatário: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Ativar o aplicativo Pais no centro de administração do Teams

O aplicativo Parents é desativado por padrão, portanto, os proprietários da equipe de classe não o verão em suas equipes de classe até que seja permitido por meio do centro de administração do Teams. O aplicativo Pais é ativado no centro de administração do Teams usando [Permitir aplicativos bloqueados pelos desenvolvedores](manage-apps.md#allow-and-block-apps).

A qualquer momento, o aplicativo pode ser desativado no nível do locatário usando [Permitir e bloquear aplicativos](manage-apps.md#allow-and-block-apps) no centro de administração do Teams. Se estiver desativado no nível do locatário, ele será bloqueado para todos os usuários, mesmo que as permissões no nível do usuário sejam ativadas.

O aplicativo Parents também pode ser desativado no nível do usuário usando [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](teams-app-permission-policies.md).

## <a name="set-a-preferred-invitation-channel"></a>Definir um canal de convite preferencial

Os administradores podem escolher email ou SMS como seu canal de convite de conexão pai preferido.

As mensagens enviadas aos pais e responsáveis estarão em texto simples, sem HTML, formatação ou estilos aplicados.

> [!NOTE]
> Se você escolher o SMS como o canal preferencial para enviar convites de Conexão Pai para pais e responsáveis, esteja ciente de que:
>
> - Os números de telefone pai e responsável devem ser formatados pelo E.164 para convites SMS e pesquisa de perfil para funcionar.
>   - Por exemplo, formate números de telefone como `+[country code][area code][phone number]`, como `+12223334444`.
> - As tarifas de SMS da operadora móvel podem ser cobradas aos pais e responsáveis que recebem convites sms.

### <a name="set-a-preferred-invite-channel-in-the-teams-admin-center"></a>Definir um canal de convite preferencial no centro de administração do Teams

1. Entre no [centro de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
1. Acesse **Configurações de Pais e responsáveis** da **Educação** > .
1. No campo **Método de contato preferencial**, selecione **Email** ou **Celular – SMS**.
1. Salve suas alterações.

### <a name="set-a-preferred-invite-channel-using-powershell"></a>Definir um canal de convite preferencial usando o PowerShell

1. Instale a *versão 4.9.0 ou superior* do módulo do Teams PowerShell em [https://www.powershellgallery.com/packages/MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams).

1. Execute o comando abaixo e entre com credenciais de administrador.

    ```powershell
    Connect-MicrosoftTeams
    ```

1. Execute o comando abaixo para exibir o valor atual para `ParentGuardianPreferredContactMethod`.

    ```powershell
    Get-CsTeamsEducationConfiguration
    ```

1. Execute um dos comandos abaixo para alterar o valor.

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod Email
    ```

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod SMS
    ```

## <a name="more-information"></a>Mais informações

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
