---
title: Gravação de reuniões na nuvem do Microsoft Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: Orientação prática para a implantação de recursos de voz em nuvem no Teams para gravar reuniões e chamadas em grupo do Teams, capturando áudio, vídeo e atividade de compartilhamento de tela.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1360847f187d98118d0b5468638cf1d6eb215fb8
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706858"
---
# <a name="teams-cloud-meeting-recording"></a>Gravação de reuniões na nuvem do Microsoft Teams

No Microsoft Teams, os usuários podem gravar reuniões e chamadas de grupo do Teams para capturar atividades de áudio, vídeo e compartilhamento de tela. Há também uma opção para habilitar a transcrição automática nas gravações. Com isso, os usuários podem reproduzir gravações de reunião com legendas ocultas e procurar itens de discussão importantes na transcrição. A gravação ocorre na nuvem e é salva no OneDrive e no SharePoint, para que os usuários possam compartilhá-la com segurança em sua organização.

Quando uma reunião é gravada, ela é automaticamente:

- Carregada no OneDrive ou no SharePoint
- Com permissão para as pessoas convidadas para a reunião
- Vinculado no chat da reunião
- Exibido na guia Gravações e Transcrições da reunião no calendário do Teams
- Adicionado a várias listas de arquivos Microsoft 365: Compartilhado comigo, office.com, Recomendado, Recente etc.
- Indexado para Microsoft 365 Search

Relacionados: [documentação da solicitação de reunião do usuário final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> A alteração do uso do Microsoft Stream (clássico) para o OneDrive e o SharePoint para gravações de reunião ocorrerá automaticamente em agosto de 2021. Para obter informações detalhadas, confira [Usar o OneDrive e SharePoint ou Stream para gravações de reunião](tmr-meeting-recording-change.md).

> [!NOTE]
> Para informações sobre o uso de funções em reuniões do Teams e como alterar as funções dos usuários, confira [Funções em uma reunião do Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019). Para opções de gravação de eventos ao vivo, confira [Políticas de gravação de eventos ao vivo no Teams](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Pré-requisitos para a gravação na nuvem do Teams

Para que as reuniões de um usuário do Teams sejam gravadas, o OneDrive e o SharePoint devem estar habilitados para o locatário. Além disso, os pré-requisitos a seguir são necessários para o organizador da reunião e para a pessoa que está iniciando a gravação:

- O usuário tem armazenamento suficiente no OneDrive para que gravações de reunião que não são do canal sejam salvas.

- O canal do Teams tem armazenamento suficiente no SharePoint para que as gravações de reunião do canal sejam salvas.

- O usuário `CsTeamsMeetingPolicy -AllowCloudRecording` configuração definida como true para gravar reuniões e chamadas em grupo.

- O usuário `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` configuração definida como true para registrar chamadas 1:1.

- O usuário não é um usuário anônimo, Convidado ou federado na reunião.

- Para habilitar a transcrição da reunião de um usuário, a política de reunião do Teams à qual ele está atribuído deve ter a configuração `-AllowTranscription` definida como true.

- Para permitir que as gravações de reunião de canal sejam salvas para que os membros do canal não possam editar ou baixar as gravações, a configuração `CSTeamsMeetingPolicy -ChannelRecordingDownload` de canal deve ser definida como Bloquear.

> [!IMPORTANT]
>
> Os usuários não precisarão do OneDrive ou do SharePoint habilitado se você quiser que os usuários gravem e baixem apenas as gravações. Isso significa que as gravações não são armazenadas no OneDrive ou no SharePoint, mas são armazenadas no armazenamento temporário do Teams com um limite de 21 dias antes de serem excluídas. Não é algo que um administrador possa controlar, gerenciar ou excluir no momento.
>
> Para obter [mais informações sobre como o armazenamento de gravação de reunião temporário funciona](#temp-storage), consulte abaixo.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar a gravação na nuvem do Teams para usuários em sua organização

Esta seção explica como você pode configurar e planejar a gravação de reuniões do Teams por meio [de reunião do Teams](policy-assignment-overview.md).

### <a name="turn-on-or-turn-off-cloud-recording"></a>Ativar ou desativar a gravação na nuvem

Você pode usar o centro de administração do Microsoft Teams ou o PowerShell para definir uma política de reunião do Teams para controlar a gravação das reuniões do usuário.

No centro de administração do Microsoft Teams, habilite ou desabilite a configuração **Gravação em nuvem** na política de reunião. Para saber mais, consulte [configurações de política de reunião para áudio e vídeo](meetings-policies-recording-and-transcription.md#cloud-recording).

Usando o PowerShell, você define a configuração AllowCloudRecording no TeamsMeetingPolicy. Para saber mais, confira [New–CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

O organizador da reunião e o iniciador de gravação precisam ter permissões de gravação para gravar a reunião. A menos que você tenha atribuído uma política personalizada aos usuários, eles receberão a política global, que tem AllowCloudRecording habilitado por padrão.

> [!NOTE]
> Para mais informações sobre o uso das funções do Teams para configurar quem tem permissão para gravar uma reunião, confira [Funções em uma reunião do Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Para que um usuário retorne à política global, use o cmdlet a seguir para remover uma atribuição de política específica para um usuário:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para alterar o valor de AllowCloudRecording na política global, use o seguinte cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|Cenário|Etapas|
|--|--|
| Quero que todos os usuários da empresa possam gravar as reuniões. | <ol><li>Confirme que o CsTeamsMeetingPolicy global tenha AllowCloudRecording = verdadeiro.<li>Todos os usuários têm as CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = verdadeiro.</ol> |
| Quero que a maioria dos meus usuários consiga gravar as reuniões, mas desabilitar seletivamente usuários específicos que não têm permissão para gravar. | <ol><li>Confirme que GlobalCsTeamsMeetingPolicy tem AllowCloudRecording = verdadeiro.<li>A maioria dos usuários têm as CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = verdadeiro.<li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowCloudRecording = false.</ol> |
| Eu quero que a gravação seja 100% desabilitada. | <ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false.<li>Todos os usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = falso. |
| Quero que a gravação seja desativada para a maioria dos usuários, mas permitir que usuários específicos possam gravar. | <ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false.<li>A maioria dos usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = falso.<li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowCloudRecording = verdadeiro. <ol> |

<a name="bd-channel"></a>

### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>Bloquear ou permitir o download de gravações de reunião de canal

Essa configuração controla se as reuniões de canal são salvas em uma pasta "Gravações" ou em uma pasta "Gravações\Exibir somente" no canal. A configuração se aplica à política do usuário que seleciona o registro para a reunião do canal.

Os dois valores para essa configuração são:

- **Permitir** (padrão) – Salva gravações de reunião de canal em uma pasta "Gravações" no canal. As permissões nos arquivos de gravação serão baseadas nas permissões do SharePoint do Canal. Isso é o mesmo que qualquer outro arquivo carregado para o canal.

- **Bloquear**— Salva gravações de reunião de canal em uma pasta "Gravações\Somente exibição" no canal. Os proprietários de canal terão direitos totais sobre as gravações nesta pasta, mas os membros do canal terão acesso de leitura sem capacidade de download.

Usando o PowerShell, você define a configuração ChannelRecordingDownload no TeamsMeetingPolicy. Para saber mais, confira [New–CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

A menos que você tenha atribuído uma política personalizada aos usuários, os usuários obterão a política Global, que tem ChannelRecordingDownload definido como Permitir por padrão.

Para que um usuário retorne à política global, use o cmdlet a seguir para remover uma atribuição de política específica para um usuário:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para alterar o valor de ChannelRecordingDownload na política Global, use o seguinte cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> A configuração ChannelRecordingDownload só está disponível no módulo do Teams PowerShell versão 2.4.1-preview ou superior. Para baixar a versão prévia mais recente do módulo, use este comando:
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>Ativar ou desativar a gravação de transcrição

Essa configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução das gravações de reunião. A pessoa que iniciou a gravação precisa dessa configuração ativada para que esses recursos funcionem com a gravação.
  
Ativar essa configuração cria uma cópia da transcrição armazenada com a gravação da reunião que habilita **Pesquisa**, **CC** e **transcrições** na gravação da reunião.

> [!NOTE]
> No momento, essa transcrição de reuniões gravadas só tem suporte para inglês (EUA), inglês (Canadá), inglês (Índia), inglês (Reino Unido), inglês (Austrália), inglês (Nova Zelândia), árabe (Emirados Árabes Unidos), árabe ( Arábia Saudita), chinês (simplificado, China), chinês (tradicional, Hong Kong), chinês (tradicional, Taiwan), tcheco (Tcheco), dinamarquês (Dinamarca), holandês (Bélgica), holandês (Países Baixos), francês (Canadá), francês (França), finlandês (Finlândia), alemão (Alemanha), grego (Grécia), hebraico (Israel), hindi (Índia), húngaro (Hungria), italiano (Itália), japonês (Japão), coreano (Coreia ), norueguês (Noruega), polonês (Polônia), português (Brasil), português (Portugal), romeno (Romênia), russo (Rússia), eslovaco (Eslováquia), espanhol (México), espanhol (Espanha), sueco (Suécia), tailandês (Tailândia), turco (Turquia), ucraniano (Ucrânia) e vietnamita (Vietnã). Eles são armazenados junto com as gravações de reunião no armazenamento em nuvem do OneDrive e do SharePoint.

Você pode usar o centro de administração do Microsoft Teams ou o PowerShell para definir uma política de reunião do Teams para controlar se o iniciador de gravação tem uma opção para transcrever a gravação da reunião.

No centro de administração do Microsoft Teams, habilite ou desabilite a configuração **permitir transcrição** na política de reunião. Para saber mais, consulte [configurações de política de reunião para áudio e vídeo](meetings-policies-recording-and-transcription.md#transcription).

Usando o PowerShell, você define a configuração AllowTranscription no TeamsMeetingPolicy. Para saber mais, confira [New–CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

A menos que você tenha atribuído uma política personalizada aos usuários, os usuários recebem a política global, que tem o AllowTranscription desabilitado por padrão.

Para que um usuário retorne à política global, use o cmdlet a seguir para remover uma atribuição de política específica para um usuário:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para alterar o valor de AllowCloudRecording na política global, use o seguinte cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

|Cenário|Etapas |
|---|---|
|Quero que todos os usuários da empresa possam transcrever ao iniciar a gravação de uma reunião. |<ol><li>Confirme que CsTeamsMeetingPolicy global tem AllowTranscription = verdadeiro. <li>Todos os usuários têm as CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowTranscription = verdadeiro. </ol>|
|Quero que a maioria dos meus usuários consiga transcrever as gravações da reunião, mas desabilite seletivamente usuários específicos que não têm permissão para transcrever. |<ol><li>Confirme que CsTeamsMeetingPolicy global tem AllowTranscription = verdadeiro. <li>A maioria dos usuários tem CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = verdadeiro. <li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = false. </ol>|
|Quero que a transcrição da gravação seja 100% desabilitada. |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowTranscription = false. <li>Todos os usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = falso. </ol>|
|Quero que as transcrição seja desabilitada para a maioria dos usuários, mas permitida seletivamente para usuários específicos que tenham permissão para transcrever. |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false. <li>A maioria dos usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = falso. <li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowCloudRecording = verdadeiro. </ol>|

### <a name="terms-of-use-acceptance"></a>Aceitação dos Termos de uso

Se sua organização tiver uma política de gravação de reunião que você deseja que os usuários aceitem antes de gravar uma reunião, use o recurso [Termos de uso do Azure Active Directory](/azure/active-directory/conditional-access/terms-of-use). Esse recurso permite que os usuários aceitem os termos de política de usuário da sua organização antes de obter acesso ao Microsoft Teams. Esse recurso não é específico para clicar no botão de registro, mas está relacionado ao uso geral do Microsoft Teams ou de outros aplicativos do Microsoft 365 em geral. Nossa sugestão é adicionar suas informações de gravação de reunião aos termos gerais de uso para usar o Microsoft Teams ou o Microsoft 365.

### <a name="set-a-custom-privacy-policy-url"></a>Definir um URL de política de privacidade personalizada

Como administrador, você pode atualizar a URL da política de privacidade de gravação e transcrição do Teams com um link personalizado para sua organização. Você pode fazer isso no [Centro de administração do Azure AD](https://aad.portal.azure.com) usando as seguintes etapas:

1. Entre no centro de administração do Azure AD.
1. Vá para **Propriedades** > **Azure Active Directory**.
1. Atualizar o campo **URL da declaração de privacidade** com o link para sua política de privacidade.

> [!NOTE]
> Se você já atualizou este campo para sua organização, não precisa fazer nenhuma alteração.

Depois de adicionar a URL da sua política de privacidade, a declaração de privacidade padrão da gravação e transcrição da reunião do Teams será substituída pela nova URL fornecida pela sua organização.

> [!NOTE]
> Os usuários anônimos, convidados e federados que ingressarem em reuniões do Teams hospedadas por sua organização ainda terão a política de privacidade de transcrição e gravação de reunião padrão do Teams.

## <a name="permissions-and-storage"></a>Permissões e armazenamento

As gravações de reunião são armazenadas no armazenamento em nuvem do OneDrive e do SharePoint. O local e as permissões dependem do tipo de reunião e da função do usuário na reunião. As permissões padrão aplicadas à gravação estão listadas abaixo, os usuários que têm direitos de edição completos no arquivo de gravação de vídeo podem alterar as permissões e compartilhá-lo posteriormente com outras pessoas, conforme necessário.

### <a name="non-channel-meetings"></a>Reuniões que não são do canal

- A gravação é armazenada em uma pasta chamada **Gravações** no OneDrive do usuário que clicou no registro. 

  Exemplo: *gravações do OneDrive*/**do gravador**

- As pessoas convidadas para a reunião, exceto os participantes externos, receberão automaticamente permissão para o arquivo de gravação com acesso de exibição sem capacidade de download.

- O proprietário da reunião e a pessoa que clicou no registro obterão acesso de edição completo com a capacidade de alterar permissões e compartilhar com outras pessoas.

### <a name="channel-meetings"></a>Reuniões de canal

Se `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` estiver definido como Permitir (padrão):

- A gravação é armazenada na biblioteca de documentação do site do Teams em uma pasta chamada **Gravações**.

  Exemplo: *Nome do Teams – Gravações de documentos de nome*/**de**/**canal**

- O membro que clicou no registro tem direitos de edição para a gravação.

- As permissões dos outros membros são baseadas nas permissões do SharePoint do canal.

Se `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` estiver definido como Bloquear:

- A gravação é armazenada na biblioteca de documentação do site do Teams em uma pasta chamada **Gravações/Exibição somente**. 

  Exemplo: *Nome do Teams - Documentos*/**/Gravações/Exibição do nome do canal**

- Os proprietários de canal terão direitos completos de edição e download nas gravações nesta pasta.

- Os membros do canal terão acesso somente exibição sem capacidade de download.

Para obter mais informações sobre tipos específicos de reunião, consulte a tabela a seguir:

| Tipo de reunião  | Quem clicou em Gravar?| Para onde vai a gravação? | Quem tem acesso? De leitura/gravação, R ou compartilhamento  |
|-------------|-----------------------|------------------------|------------------------|
|Chamada privada com participantes internos             |Chamador                 |Conta do OneDrive do chamador                        |O chamador é proprietário e tem todos os direitos. <br /><br />O receptor (se estiver no mesmo locatário) tem acesso somente leitura. Sem acesso de compartilhamento. <br /><br /> O receptor da chamada (se estiver em outro locatário) não tem acesso. O chamador deve compartilhá-lo com o receptor da chamada.|
|Chamada privada com participantes internos             |Receptor da chamada                 |Conta do OneDrive do destinatário da chamada                        |O receptor da chamada é proprietário e tem todos os direitos. <br /><br />Chamador (se no mesmo locatário tiver acesso somente leitura. Sem acesso de compartilhamento. <br /><br />O chamador (se estiver em outro locatário) não tem acesso. O receptor da chamada deve compartilhá-lo com o chamador.|
|Chamada privada com uma chamada externa             |Chamador                 |Conta do OneDrive do chamador                        |O chamador é proprietário e tem todos os direitos.<br /> <br />O receptor da chamada não tem acesso. O chamador deve compartilhá-lo com o receptor da chamada.|
|Chamada privada com uma chamada externa             |Receptor da chamada                 |Conta do OneDrive do destinatário da chamada                        |O receptor da chamada é proprietário e tem todos os direitos.<br /><br />O chamador não tem acesso. O receptor da chamada deve compartilhá-lo com o chamador.|
|Chamada em grupo                                 |Qualquer membro da chamada |Membro do grupo que clicou na conta do OneDrive do registro  |O membro que clicou em Gravar tem todos os direitos. <br /><br /> Outros membros do mesmo locatário têm direitos de leitura. <br /><br /> Outros membros do grupo de locatários diferentes não têm direitos sobre ele.|
|Reunião agendada/adhoc                    |Organizador              |Conta do OneDrive do organizador                     |O organizador tem todos os direitos à gravação. <br /><br /> Todos os outros membros da reunião têm acesso de leitura sem capacidade de download.|
|Reunião agendada/adhoc                    |Outro membro da reunião   |Membro da reunião que clicou em Gravar                                  |O membro que clicou em Gravar tem todos os direitos à gravação. <br /><br />O organizador tem direitos de edição e pode compartilhar.<br /><br /> Todos os outros membros da reunião têm acesso de leitura sem capacidade de download.|
|Reunião ad hoc/agendada com participantes externos|Organizador              |Conta do OneDrive do organizador                     |O organizador tem todos os direitos à gravação.<br /> <br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura sem capacidade de download. <br /><br /> Todos os outros membros externos não têm acesso e o organizador deve compartilhá-lo com eles.|
|Reunião ad hoc/agendada com participantes externos|Outro membro da reunião   |Membro que clicou em Gravar                                  |O membro que clicou em Gravar tem todos os direitos à gravação. O organizador tem direitos de edição e pode compartilhar. <br /><br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura sem capacidade de download. <br /><br />Todos os outros membros externos não têm acesso e o organizador deve compartilhá-lo com eles.|
|Reunião de canal                            |Membro do canal         |Local do SharePoint do Teams daquele canal                   |Se Set-CsTeamsMeetingPolicy -ChannelRecordingDownload estiver definido como Permitir (padrão), o membro que clicou em Registro terá direitos de edição para a gravação. As permissões dos outros membros são baseadas nas permissões do SharePoint do canal.<Br><Br>Se Set-CsTeamsMeetingPolicy -ChannelRecordingDownload estiver definido como Bloquear os proprietários do canal terão direitos totais na gravação, mas os membros do canal terão acesso de leitura sem capacidade de download.|

<a name="temp-storage"></a>

### <a name="temporary-storage-when-unable-to-upload-to-onedrive-and-sharepoint"></a>Armazenamento temporário quando não é possível carregar no OneDrive e no SharePoint

Se uma gravação de reunião não conseguir ser carregada no OneDrive e no SharePoint, ela ficará temporariamente disponível para download do Teams por 21 dias antes de ser excluída. Não é algo neste ponto que um administrador pode controlar ou gerenciar para incluir a capacidade de excluí-lo.

As gravações de reunião podem acabar neste armazenamento temporário pelos seguintes motivos:

- Para reuniões que não são de canal, se o usuário que está gravando não tem o OneDrive ou seu OneDrive atingiu sua cota de armazenamento
- Para uma reunião de canal, se o site do SharePoint atingiu sua cota de armazenamento ou o site ainda não foi provisionado
- Se políticas específicas do OneDrive e do SharePoint forem habilitadas, restringindo os usuários de carregar arquivos quando não estiver em intervalos de IP específicos, etc.

A retenção de gravação para isso é um armazenamento temporário que é afetado pela própria mensagem de chat. Dessa forma, qualquer exclusão da mensagem de chat original para a gravação impedirá que os usuários possam acessar a gravação. Há dois cenários que podem afetar isso:

- **O usuário exclui manualmente a mensagem de chat**— Nesse cenário, à medida que a mensagem original desaparecer, os usuários não poderão mais acessar a gravação e nenhum download adicional será possível. No entanto, a gravação ainda poderá ser retida nos sistemas internos da Microsoft por um tempo (sem exceder o período original de 21 dias).

- **A gravação da mensagem de chat é excluída pela política de retenção de chat**— As gravações de armazenamento temporário estão diretamente vinculadas à política de retenção de chat. Dessa forma, embora as gravações no armazenamento temporário do Teams sejam mantidas por padrão por 21 dias antes de serem excluídas, se a mensagem de chat for excluída antes do período de 21 dias, devido a políticas de retenção de mensagens de chat, a gravação também será excluída. Não é possível recuperar a gravação depois disso.

### <a name="planning-for-storage"></a>Planejar o armazenamento

O tamanho de uma gravação de 1 hora é de 400 MB. Certifique-se de entender a capacidade necessária para arquivos gravados e ter armazenamento suficiente disponível no OneDrive e no SharePoint.  Leia [Definir o espaço de armazenamento padrão para o OneDrive](/onedrive/set-default-storage-space) e [Gerenciar os limites de armazenamento do site do SharePoint](/sharepoint/manage-site-collection-storage-limits) para entender o armazenamento base incluído na assinatura e como comprar armazenamento adicional.
  
## <a name="manage-meeting-recordings"></a>Gerenciar gravações de reunião

As gravações de reunião são armazenadas como arquivos de vídeo no OneDrive e no SharePoint e seguem as opções de gerenciamento e governança disponíveis nessas plataformas. Leia a [visão geral de governança do SharePoint](/sharepoint/governance-overview) para obter mais informações.

Para reuniões que não são de canal, as gravações são armazenadas no OneDrive do gravador, portanto, o controle da propriedade e retenção depois que um funcionário sair seguirá o [processo do OneDrive e do SharePoint](/onedrive/retention-and-deletion#the-onedrive-deletion-process) normal.

As gravações de reunião têm um tempo de expiração padrão de 120 dias. Você pode desativar a configuração reuniões expiram automaticamente ou alterar o tempo de expiração padrão. Saiba mais sobre [a expiração automática das gravações de reunião](meetings-policies-recording-and-transcription.md#meetings-automatically-expire).

## <a name="closed-captions-for-recordings"></a>Legendas ocultas para gravações

As legendas ocultas para gravações de reunião do Teams estarão disponíveis durante a reprodução somente se o usuário tiver ativado a transcrição no momento da gravação. Os administradores devem [ativar a transcrição da gravação por meio da política](#turn-on-or-turn-off-recording-transcription) para garantir que os usuários tenham a opção de gravar as reuniões com transcrição.

As legendas ajudam a criar conteúdo inclusivo para visualizadores de todas as habilidades. Como proprietário, você pode ocultar legendas na gravação da reunião, embora a transcrição da reunião ainda esteja disponível no Teams, a menos que você a exclua lá.

As legendas ocultas de hoje para o arquivo de vídeo de gravação estão vinculadas à transcrição da reunião do Teams. Esse link permanecerá durante o tempo de vida do arquivo na maioria dos casos, mas poderá ser interrompido se o arquivo de vídeo for copiado no mesmo site do OneDrive ou do SharePoint, o que resultaria em legendas não disponíveis no arquivo de vídeo copiado.

Quaisquer alterações futuras no link entre a transcrição no Teams e a gravação serão esclarecidas aqui e nas notificações do centro de mensagens. Se fizermos qualquer alteração no futuro, garantiremos que os arquivos de gravação com menos de 60 dias exibam a transcrição da reunião como legendas.

> [!NOTE]
> A transcrição da reunião ainda não está disponível na GCC.

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>Descoberta Eletrônica e Conformidade para gravações de reunião

### <a name="ediscovery"></a>Descoberta Eletrônica

As gravações de reunião são armazenadas no OneDrive e no SharePoint, que é compatível com o Microsoft 365 e Office 365 Tier-D. Para dar suporte a solicitações de descoberta eletrônica para administradores de conformidade interessados em gravações de reunião ou chamada, a mensagem de gravação concluída está disponível na funcionalidade de pesquisa de conteúdo de conformidade do Microsoft Teams. Os administradores de conformidade podem procurar a palavra-chave "gravação" na linha do assunto do item na visualização de pesquisa de conteúdo de conformidade e descobrir as gravações da reunião e de chamadas na organização.

Além disso, o arquivo de vídeo da gravação de reunião pode ser encontrado por meio de pesquisas de Descoberta Eletrônica de arquivos no SharePoint e no OneDrive.

Para saber mais sobre a Descoberta Eletrônica, consulte o artigo [soluções de Descoberta Eletrônica para Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Políticas de retenção

Você pode aplicar rótulos de retenção automática para direcionar apenas arquivos de vídeo de gravação de reunião do Teams por meio da propriedade ProgID. Para obter mais informações, [como aplicar automaticamente um rótulo de retenção para gravações de reunião do Teams](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings).

### <a name="microsoft-purview-data-loss-prevention-dlp-policies"></a>Políticas DLP (Prevenção contra Perda de Dados) do Microsoft Purview

Você pode aplicar políticas DLP a arquivos de gravação de reunião também pela propriedade ProgID. Na regra DLP de arquivos no SharePoint e no OneDrive, defina as condições da seguinte maneira:

- Propriedade document = *ProgID*
- Valor = *Media.Meeting*

Para saber mais sobre a DLP, consulte o artigo [saiba mais sobre a prevenção contra perda de dados](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="meeting-recording-diagnostic-tools"></a>Ferramentas de Diagnóstico de Gravação da Reunião

### <a name="user-cannot-record-meetings"></a>O usuário não pode gravar reuniões

Se você for um administrador, poderá usar a seguinte ferramenta de diagnóstico para validar se o usuário está configurado corretamente para gravar uma reunião no Teams:

1. Selecione **Executar testes** abaixo, o que preencherá o diagnóstico no Centro de Administração do Microsoft 365.

   > [!div class="nextstepaction"]
   > [Executar testes: gravação de reunião](https://aka.ms/MeetingRecordingDiag)

2. No painel Executar diagnóstico, insira o email do usuário que não pode gravar reuniões no campo **Nome de Usuário ou Email** e selecione **Executar Testes**.

3. Os testes retornarão as melhores próximas etapas para resolver quaisquer configurações de locatário ou política para validar se o usuário está configurado corretamente para gravar uma reunião no Teams.
  
### <a name="meeting-record-is-missing"></a>Registro de reunião ausente

Se você for um administrador, poderá usar a seguinte ferramenta de diagnóstico para validar se a gravação da reunião foi concluída com êxito e se ela foi carregada no Stream ou no OneDrive, com base na ID da reunião e na hora de início da gravação:

1. Selecione **Executar testes** abaixo, o que preencherá o diagnóstico no Centro de Administração do Microsoft 365.

   > [!div class="nextstepaction"]
   > [Executar testes: gravação de reunião ausente](https://aka.ms/MissingRecordingDiag)

2. No painel Executar diagnóstico, insira a URL da reunião na **URL** da reunião que foi registrado no campo (geralmente encontrado no convite da reunião), bem como a data da reunião no campo Quando a reunião foi registrada **?** E, em seguida, selecione Executar **Testes.**

3. Os testes validam se a gravação da reunião foi concluída com êxito e foi carregada no Stream ou no OneDrive.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
