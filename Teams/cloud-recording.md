---
title: Gravação de reuniões na nuvem do Microsoft Teams
author: tonysmit
ms.author: tonysmit
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
ms.openlocfilehash: a4008aa9f69f525e3fbbeb6fd7596822d7ac9be8
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536892"
---
# <a name="teams-cloud-meeting-recording"></a>Gravação de reuniões na nuvem do Microsoft Teams

No Microsoft Teams, os usuários podem gravar reuniões e chamadas de grupo do Teams para capturar atividades de áudio, vídeo e compartilhamento de tela. Há também uma opção para habilitar a transcrição automática nas gravações. Com isso, os usuários podem reproduzir gravações de reunião com legendas ocultas e procurar itens de discussão importantes na transcrição. A gravação ocorre na nuvem e é salva no Microsoft Stream, para que os usuários possam compartilhá-la com segurança na organização.

Quando uma reunião é gravada, ela é automaticamente:

- Carregado no OneDrive for Business ou no SharePoint Online
- Com permissão para as pessoas convidadas para a reunião
- Vinculado no chat da reunião
- Exibido na guia Gravações e Transcrições da reunião no calendário do Teams
- Adicionado a várias listas de arquivos Microsoft 365: Compartilhado comigo, office.com, Recomendado, Recente etc.
- Indexado para Microsoft 365 Search

Relacionados: [documentação da solicitação de reunião do usuário final](https://support.microsoft.com/en-us/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> A alteração do uso Microsoft Stream (clássico) para o OneDrive for Business e o SharePoint Online para gravações de reunião ocorrerá automaticamente em agosto de 2021. Para obter informações detalhadas, consulte [Use OneDrive for Business SharePoint Online ou Stream para gravações de reunião](tmr-meeting-recording-change.md).

> [!NOTE]
> Para informações sobre o uso de funções em reuniões do Teams e como alterar as funções dos usuários, confira [Funções em uma reunião do Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019). Para opções de gravação de eventos ao vivo, confira [Políticas de gravação de eventos ao vivo no Teams](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Pré-requisitos para a gravação na nuvem do Teams

Para que as reuniões de um usuário do Teams sejam gravadas, OneDrive for Business e o SharePoint Online devem ser habilitados para o locatário. Além disso, os pré-requisitos a seguir são necessários para o organizador da reunião e para a pessoa que está iniciando a gravação:

- O usuário tem armazenamento suficiente no OneDrive for Business para que gravações de reunião que não sejam de canal sejam salvas.

- O canal do Teams tem armazenamento suficiente no SharePoint Online para que as gravações de reunião do canal sejam salvas.

- O usuário `CsTeamsMeetingPolicy -AllowCloudRecording` configuração definida como true para gravar reuniões e chamadas em grupo.

- O usuário `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` configuração definida como true para registrar chamadas 1:1.

- O usuário não é um usuário anônimo, Convidado ou federado na reunião.

- Para habilitar a transcrição da reunião de um usuário, a política de reunião do Teams à qual ele está atribuído deve ter a configuração `-AllowTranscription` definida como true.

- Para permitir que as gravações de reunião de canal sejam salvas para que os membros do canal não possam editar ou baixar as gravações, a configuração `CSTeamsMeetingPolicy -ChannelRecordingDownload` de canal deve ser definida como Bloquear.

> [!IMPORTANT]
>
> Os usuários não precisarão OneDrive for Business ou o SharePoint Online habilitado se você quiser que os usuários gravem e baixem apenas as gravações. Isso significa que as gravações não são armazenadas no OneDrive for Business ou no SharePoint Online, mas são armazenadas no armazenamento temporário do Teams com um limite de 21 dias antes de serem excluídas. Não é algo que um administrador possa controlar, gerenciar ou excluir no momento.
>
> Para obter [mais informações sobre como o armazenamento de gravação de reunião temporário funciona](#temp-storage), consulte abaixo.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar a gravação na nuvem do Teams para usuários em sua organização

Esta seção explica como você pode configurar e planejar a gravação de reuniões do Teams por meio [de reunião do Teams](policy-assignment-overview.md).

### <a name="turn-on-or-turn-off-cloud-recording"></a>Ativar ou desativar a gravação na nuvem

Você pode usar o centro de administração do Microsoft Teams ou o PowerShell para definir uma política de reunião do Teams para controlar a gravação das reuniões do usuário.

No centro de administração do Microsoft Teams, habilite ou desabilite a configuração **Permitir gravação na nuvem** na política de reunião. Para saber mais, consulte [configurações de política de reunião para áudio e vídeo](meetings-policies-recording-and-transcription.md#allow-cloud-recording).

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

- **Permitir** (padrão) – Salva gravações de reunião de canal em uma pasta "Gravações" no canal. As permissões nos arquivos de gravação serão baseadas nas permissões do SharePoint Online do Canal. Isso é o mesmo que qualquer outro arquivo carregado para o canal.

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

Essa configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução das gravações de reunião. Se você desativar essa opção, as opções **Pesquisar** e **CC** não estarão disponíveis durante a reprodução de uma gravação de reunião. A pessoa que iniciou a gravação precisa dessa configuração ativada para que a gravação também inclua a transcrição.

> [!NOTE]
> Essa transcrição para reuniões gravadas é atualmente suportada apenas para inglês (EUA), inglês (Canadá), inglês (Índia), inglês (Reino Unido), inglês (Austrália), inglês (Nova Zelândia), alemão (Alemanha), português (Brasil ), holandês (Países Baixos), holandês (Bélgica), francês (França), espanhol (Espanha), japonês (Japão), francês (Canadá), chinês (cantonês, tradicional), chinês (mandarim, simplificado), hindi (Índia), italiano (Itália), coreano (Coreia), espanhol (México), sueco (Suécia), polonês (Polônia), árabe (Emirados Árabes Unidos), árabe (Arábia Saudita), dinamarquês (Dinamarca), finlandês (Finlândia), norueguês (Noruega) e russo (Rússia). Eles são armazenados junto com as gravações de reunião no OneDrive for Business armazenamento em nuvem do SharePoint Online.

Você pode usar o centro de administração do Microsoft Teams ou o PowerShell para definir uma política de reunião do Teams para controlar se o iniciador de gravação tem uma opção para transcrever a gravação da reunião.

No centro de administração do Microsoft Teams, habilite ou desabilite a configuração **permitir transcrição** na política de reunião. Para saber mais, consulte [configurações de política de reunião para áudio e vídeo](meetings-policies-recording-and-transcription.md#allow-transcription).

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

</br>
</br>

|Cenário|Etapas |
|---|---|
|Quero que todos os usuários da empresa possam transcrever ao iniciar a gravação de uma reunião. |<ol><li>Confirme que CsTeamsMeetingPolicy global tem AllowTranscription = verdadeiro. <li>Todos os usuários têm as CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudTranscription = verdadeiro. </ol>|
|Quero que a maioria dos meus usuários consiga transcrever as gravações da reunião, mas desabilite seletivamente usuários específicos que não têm permissão para transcrever. |<ol><li>Confirme que CsTeamsMeetingPolicy global tem AllowTranscription = verdadeiro. <li>A maioria dos usuários tem CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = verdadeiro. <li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = false. </ol>|
|Quero que a transcrição da gravação seja 100% desabilitada. |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowTranscription = false. <li>Todos os usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = falso. </ol>|
|Quero que as transcrição seja desabilitada para a maioria dos usuários, mas permitida seletivamente para usuários específicos que tenham permissão para transcrever. |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false. <li>A maioria dos usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = falso. <li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowCloudRecording = verdadeiro. </ol>|

### <a name="terms-of-use-acceptance"></a>Aceitação dos Termos de uso
Se sua organização tiver uma política de gravação de reunião que você deseja que os usuários aceitem antes de gravar uma reunião, use o recurso [Termos de uso do Azure Active Directory](/azure/active-directory/conditional-access/terms-of-use). Esse recurso permite que os usuários aceitem os termos de política de usuário da sua organização antes de obter acesso ao Microsoft Teams. Esse recurso não é específico para clicar no botão de registro, mas está relacionado ao uso geral do Microsoft Teams ou de outros aplicativos do Microsoft 365 em geral. Nossa sugestão é adicionar suas informações de gravação de reunião aos termos gerais de uso para usar o Microsoft Teams ou o Microsoft 365. 

## <a name="permissions-and-storage"></a>Permissões e armazenamento

As gravações de reunião são armazenadas no OneDrive for Business armazenamento em nuvem do SharePoint Online. O local e as permissões dependem do tipo de reunião e da função do usuário na reunião. As permissões padrão aplicadas à gravação estão listadas abaixo, os usuários que têm direitos de edição completos no arquivo de gravação de vídeo podem alterar as permissões e compartilhá-lo posteriormente com outras pessoas, conforme necessário.

### <a name="non-channel-meetings"></a>Reuniões que não são do canal

- A gravação é armazenada em uma pasta chamada **Gravações** no OneDrive for Business do usuário que clicou no registro. 

  Exemplo: <i>gravação do gravador OneDrive for Business</i>/**gravação**

- As pessoas convidadas para a reunião, exceto usuários externos, receberão automaticamente permissão para o arquivo de gravação com acesso de exibição sem capacidade de download.

- O proprietário da reunião e a pessoa que clicou no registro obterão acesso de edição completo com a capacidade de alterar permissões e compartilhar com outras pessoas.

### <a name="channel-meetings"></a>Reuniões de canal

Se `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` estiver definido como Permitir (padrão):

- A gravação é armazenada na biblioteca de documentação do site do Teams em uma pasta chamada **Gravações**.

  Exemplo: <i>teams - Nome do canal</i>/**documentos**/**gravações**

- O membro que clicou no registro tem direitos de edição para a gravação.

- As permissões de todos os outros membros se baseiam nas permissões do SharePoint Online do Canal.

Se `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` estiver definido como Bloquear:

- A gravação é armazenada na biblioteca de documentação do site do Teams em uma pasta chamada **Gravações/Exibição somente**. 

  Exemplo: <i>teams - Nome do canal</i>/**Documentos/Gravações/Exibir somente**

- Os proprietários de canal terão direitos completos de edição e download nas gravações nesta pasta.

- Os membros do canal terão acesso somente ao modo de exibição sem capacidade de download.

Para obter mais informações sobre tipos específicos de reunião, consulte a tabela a seguir:

| Tipo de reunião  | Quem clicou em Gravar?| Para onde vai a gravação? | Quem tem acesso? De leitura/gravação, R ou compartilhamento  |
|-------------|-----------------------|------------------------|------------------------|
|Chamada privada com participantes internos             |Chamador                 |Conta do OneDrive for Business do chamador                        |O chamador é proprietário e tem todos os direitos. <br /><br />O receptor (se estiver no mesmo locatário) tem acesso somente leitura. Sem acesso de compartilhamento. <br /><br /> O receptor da chamada (se estiver em outro locatário) não tem acesso. O chamador deve compartilhá-lo com o receptor da chamada.|
|Chamada privada com participantes internos             |Receptor da chamada                 |Conta do OneDrive for Business do receptor da chamada                        |O receptor da chamada é proprietário e tem todos os direitos. <br /><br />Chamador (se no mesmo locatário tiver acesso somente leitura. Sem acesso de compartilhamento. <br /><br />O chamador (se estiver em outro locatário) não tem acesso. O receptor da chamada deve compartilhá-lo com o chamador.|
|Chamada privada com uma chamada externa             |Chamador                 |Conta do OneDrive for Business do chamador                        |O chamador é proprietário e tem todos os direitos.<br /> <br />O receptor da chamada não tem acesso. O chamador deve compartilhá-lo com o receptor da chamada.|
|Chamada privada com uma chamada externa             |Receptor da chamada                 |Conta do OneDrive for Business do receptor da chamada                        |O receptor da chamada é proprietário e tem todos os direitos.<br /><br />O chamador não tem acesso. O receptor da chamada deve compartilhá-lo com o chamador.|
|Chamada em grupo                                 |Qualquer membro da chamada |Membro do grupo que clicou na conta do OneDrive for Business da Gravação  |O membro que clicou em Gravar tem todos os direitos. <br /><br /> Outros membros do mesmo locatário têm direitos de leitura. <br /><br /> Outros membros do grupo de locatários diferentes não têm direitos sobre ele.|
|Reunião agendada/adhoc                    |Organizador              |Conta do OneDrive for Business do organizador                     |O organizador tem todos os direitos à gravação. <br /><br /> Todos os outros membros da reunião têm acesso de leitura sem capacidade de download.|
|Reunião agendada/adhoc                    |Outro membro da reunião   |Membro da reunião que clicou em Gravar                                  |O membro que clicou em Gravar tem todos os direitos à gravação. <br /><br />O organizador tem direitos de edição e pode compartilhar.<br /><br /> Todos os outros membros da reunião têm acesso de leitura sem capacidade de download.|
|Reunião agendada/adhoc com usuários externos|Organizador              |Conta do OneDrive for Business do organizador                     |O organizador tem todos os direitos à gravação.<br /> <br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura sem capacidade de download. <br /><br /> Todos os outros membros externos não têm acesso e o organizador deve compartilhá-lo com eles.|
|Reunião agendada/adhoc com usuários externos|Outro membro da reunião   |Membro que clicou em Gravar                                  |O membro que clicou em Gravar tem todos os direitos à gravação. O organizador tem direitos de edição e pode compartilhar. <br /><br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura sem capacidade de download. <br /><br />Todos os outros membros externos não têm acesso e o organizador deve compartilhá-lo com eles.|
|Reunião de canal                            |Membro do canal         |Localização do SharePoint Online do Teams para esse canal                   |Se Set-CsTeamsMeetingPolicy -ChannelRecordingDownload estiver definido como Permitir (padrão), o membro que clicou em Registro terá direitos de edição para a gravação. As permissões de todos os outros membros se baseiam nas permissões do SharePoint Online do Canal.<Br><Br>Se Set-CsTeamsMeetingPolicy -ChannelRecordingDownload estiver definido como Bloquear os proprietários do canal terão direitos totais na gravação, mas os membros do canal terão acesso de leitura sem capacidade de download.|

<a name="temp-storage"></a>
### <a name="temporary-storage-when-unable-to-upload-to-onedrive-for-business-and-sharepoint-online"></a>Armazenamento temporário quando não é possível carregar para o OneDrive for Business e o SharePoint Online

Se uma gravação de reunião não for capaz de ser carregada no OneDrive for Business e no SharePoint Online, ela estará temporariamente disponível para download do Teams por 21 dias antes de ser excluída. Não é algo neste ponto que um administrador pode controlar ou gerenciar para incluir a capacidade de excluí-lo.

As gravações de reunião podem acabar neste armazenamento temporário pelos seguintes motivos:

- Para reuniões que não são do canal, se a gravação do usuário não tiver um OneDrive for Business configurado ou se o OneDrive for Business tiver atingido sua cota de armazenamento
- Para uma reunião de canal se o site do SharePoint Online atingiu sua cota de armazenamento ou o site ainda não foi provisionado
- Se as OneDrive for Business e as políticas do SharePoint Online estão habilitadas, restringindo os usuários de carregar arquivos quando não estão em intervalos de IP específicos, etc.

A retenção de gravação para isso é um armazenamento temporário que é afetado pela própria mensagem de chat. Dessa forma, qualquer exclusão da mensagem de chat original para a gravação impedirá que os usuários possam acessar a gravação. Há dois cenários que podem afetar isso:

- **O usuário exclui manualmente a mensagem de chat**— Nesse cenário, à medida que a mensagem original desaparecer, os usuários não poderão mais acessar a gravação e nenhum download adicional será possível. No entanto, a gravação ainda poderá ser retida nos sistemas internos da Microsoft por um tempo (sem exceder o período original de 21 dias).

- **A gravação da mensagem de chat é excluída pela política de retenção de chat**— As gravações de armazenamento temporário estão diretamente vinculadas à política de retenção de chat. Dessa forma, embora as gravações no armazenamento temporário do Teams sejam mantidas por padrão por 21 dias antes de serem excluídas, se a mensagem de chat for excluída antes do período de 21 dias, devido a políticas de retenção de mensagens de chat, a gravação também será excluída. Não é possível recuperar a gravação depois disso.

### <a name="planning-for-storage"></a>Planejar o armazenamento

O tamanho de uma gravação de 1 hora é de 400 MB. Certifique-se de entender a capacidade necessária para arquivos gravados e ter armazenamento suficiente disponível no OneDrive for Business e no SharePoint Online.  Leia [Definir o espaço de armazenamento padrão para o OneDrive for Business](/onedrive/set-default-storage-space) e o [Gerenciar limites de armazenamento de site do SharePoint Online](/sharepoint/manage-site-collection-storage-limits) para entender o armazenamento base incluído na assinatura e como comprar armazenamento adicional.

 <a name="auto-expiration"></a>
### <a name="auto-expiration-of-teams-meeting-recordings"></a>Expiração automática de gravações de reunião do Teams: 

> [!IMPORTANT]
>
> O recurso de expiração automática discutido neste artigo ainda não foi iniciado. Consulte [o roteiro (ID do recurso: 84580)](https://www.microsoft.com/microsoft-365/roadmap?searchterms=82057&filters=&searchterms=84580) para obter mais informações sobre sua data de entrega.
> 
> Estamos fornecendo informações sobre como esse recurso funcionará no futuro, para que você possa planejar essa alteração e modificar as configurações de política do Teams com antecedência.
>
> O comando para alterar preventivamente a configuração de expiração padrão no Teams está atualmente em implantação, mas você pode ver o atributo no PowerShell. No momento, a configuração não está disponível nos centros de administração do Teams. Essas configurações estarão disponíveis e serão comunicadas em uma postagem do centro de mensagens pelo menos 30 dias antes de lançarmos o recurso.
>
>

Consulte as perguntas frequentes para administradores e usuários finais coletarem insights sobre como a expiração automática das gravações de reunião do Teams funcionará, quais ações você pode executar agora e quais ações você pode executar após o lançamento do recurso.
  
## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Qual é a mudança?**
  
Estamos introduzindo uma configuração de expiração padrão de 60 dias para todas as TMRs (gravações de reunião) do Teams recém-criadas. Isso significa que, por padrão, todas as TMRs criadas após habilitarmos esse recurso serão excluídas 60 dias após a data de criação. Se os administradores desejarem que as gravações de reunião expirem mais cedo ou mais tarde do que o padrão, eles poderão modificar a configuração de expiração. Os sistemas do OneDrive e do SharePoint monitorarão a data de validade definida em todas as gravações de reunião e as moverão automaticamente para a lixeira na data de validade.

**A quem isso afeta?**
  
Qualquer pessoa que armazene uma gravação de reunião do Teams (não canal, canal ou reunião ad hoc) no OneDrive ou no SharePoint.

**Por que devo usar esse recurso?**
  
Você deve usar esse recurso para limitar o armazenamento do OneDrive ou do SharePoint consumido pelas gravações de reunião do Teams (observação: elas normalmente usam cerca de 400 MB por hora de gravação).
  
**Por que estamos introduzindo essa alteração?**
  
Os clientes forneceram um número enorme de comentários de que desejam mais controles para reduzir a confusão de armazenamento criada com base em gravações de reuniões do Teams, 99% das quais, em média, nunca são re-assistidas após 60 dias.
  
**Por que isso está sendo ativado por padrão?**
  
Acreditamos que quase todos os clientes se beneficiarão da carga de armazenamento reduzida em seu locatário removendo gravações que provavelmente nunca serão re-assistidas após 60 dias. É nossa meta fornecer uma experiência o mais limpa possível para todos os clientes por padrão.
  
**Serão excluídos automaticamente mesmo se os dados forem acessados ou baixados?**
  
Acessar o arquivo não altera a data de expiração.
  
**A data de expiração é visível como uma coluna na lista?**

Todos com acesso de visualização verão um ícone vermelho ao lado do arquivo na pasta do OneDrive ou do Microsoft Office SharePoint Online 14 dias antes que o arquivo expire. Atualmente, não há nenhuma maneira de adicionar uma coluna a uma lista com data de expiração.
  
**Como a data de expiração é calculada?**
  
A data de expiração é calculada como o dia em que a gravação da reunião é criada, além do número padrão de dias definido na configuração do Teams pelo administrador.
  
**A data de expiração pode ser alterada para cada TMR, como dados A com data de expiração de 30 dias e a dados B com expiração de 60 dias?**

Sim, a data de validade é definida por arquivo. Os usuários podem modificar a data de validade no painel de detalhes de um arquivo selecionado no OneDrive ou no SharePoint.

**Como um administrador pode alterar a data de expiração?**
  
Os administradores poderão alterar a configuração de expiração padrão no PowerShell ou no centro de administração do Teams antes do lançamento do recurso. Alterar as configurações de expiração afetará apenas TMRs recém-criados desse ponto em diante. Isso não afetará as gravações feitas antes dessa data. As novas gravações não expiram automaticamente até que o recurso seja lançado, mesmo que você possa definir o atributo de política antes de ser lançado.

Os valores dos dias de expiração podem ser definidos da seguinte forma:
  
- O valor pode ser de 1 a 9.999.
- O valor também pode ser -1 para definir TMR para nunca expirar. 
 
Os administradores não podem alterar a data de expiração de TMRs existentes já carregados no OneDrive ou no Microsoft Office SharePoint Online antes do lançamento desse recurso. Isso protege a intenção do usuário que possui a TMR.
  
Para alterar o comportamento padrão de expiração automática para seu locatário, modifique o atributo a seguir no PowerShell. Neste exemplo, o padrão é alterado para 50 dias.
 
Set-CsTeamsMeetingPolicy -Identity Global -**New** MeetingRecordingExpirationDays 50

A capacidade de alterar a configuração padrão no centro de administração do Teams será implantada posteriormente, pelo menos 30 dias antes de ativarmos o recurso de expiração automática por padrão.
  
**Um administrador pode definir TMRs para nunca expirar?**
  
 Sim, os administradores podem definir TMRs para nunca expirar.
  
**Reproduzir a gravação altera a data de expiração?**

Não, a reprodução não afeta a data de expiração.
  
**O que acontecerá com a data de expiração se o TMR for baixado e carregado novamente?**

A data de expiração será removida após o recarregamento, independentemente da SKU do usuário.
  
**O que acontece se eu copiar ou mover o TMR para um local ou site diferente?**

A data é mantida apenas para um arquivo TMR movido. Um arquivo copiado não terá a data de validade, assim como um TMR carregado novamente.
  

**Qual o escopo de controle para a política de administração?**
  
As reuniões e chamadas serão controladas pela mesma `CsTeamsMeetingPolicy`configuração, `MeetingRecordingExpirationDays`. 
  
**Como os usuários finais podem modificar a data de expiração em um arquivo TMR específico?**
  
Qualquer pessoa que tenha permissões de edição e exclusão em uma TMR pode modificar a data de validade no painel de detalhes do arquivo no OneDrive ou no SharePoint.

O usuário pode adiar a expiração por 14, 30 ou 60 dias, ou pode escolher uma data específica no futuro ou pode selecionar que o arquivo nunca expirou.
  
**Os administradores com experiência dependem desse recurso para conformidade e segurança estritas?**
  
Não, os administradores não devem depender desse recurso para proteção legal, pois os usuários finais podem modificar a data de expiração de todas as gravações que controlam.
  
**Esse recurso aplicará a retenção de arquivos?**
  
Não, os arquivos não serão retidos devido a esse recurso ou suas configurações. Se um usuário com permissões de exclusão tentar excluir um TMR que tenha uma configuração de expiração, a ação de exclusão desse usuário será executada.

**A política de retenção e/ou exclusão que defini no centro de segurança e conformidade (S+C) substitui a configuração de expiração de TMR?**
  
Sim, todas as políticas definidas no centro S+C terão precedência total. Por exemplo:
  
- Se você tiver uma política que diz que todos os arquivos em um site devem ser retidos por 100 dias e a configuração de expiração de uma TMR for de 30 dias, o arquivo de gravação será mantido pelos 100 dias completos.  
- Se você tiver uma política de exclusão que diz que todas as TMRs serão excluídas após cinco dias e você tiver uma configuração de expiração em um arquivo de gravação de 30 dias, esse arquivo será excluído após cinco dias.

**O que acontece quando uma TMR “expira”?**
  
Na data de validade, a TMR é movida para a lixeira do OneDrive ou do SharePoint e o campo de data de expiração é limpo. Essa ação pelo sistema é exatamente a mesma que se um usuário excluiu o arquivo. O ciclo de vida da lixeira seguirá o caminho normal posteriormente. Se o usuário recuperar a TMR da lixeira, a TMR não será excluída por esse recurso novamente, pois a data de validade foi desmarcada, a menos que o usuário final defina uma nova data de expiração no arquivo.
  
**Como eu vou ser notificado sobre a expiração de um arquivo?**
  
Todas as pessoas com acesso de visualização verão uma notificação sobre a data de validade no intervalo de gravação na janela de chat do Teams.
  
Todos com acesso de visualização verão um ícone vermelho ao lado do arquivo na pasta do OneDrive ou do SharePoint 14 dias antes que o arquivo expire.
  
O proprietário do arquivo receberá uma notificação por email quando a TMR expirar e será direcionado para a lixeira para recuperar a TMR se desejar fazer isso.
  
**Quais SKUs são necessários para esse recurso?**
  
Todas as SKUs terão esse recurso por padrão. Usuários A1 terão o padrão de um período de expiração de 30 dias.
  
**O arquivo expirar é um evento auditado e eu posso vê-lo em meus logs de auditoria?**
  
Sim, as expirações de arquivo aparecerão como eventos de exclusão do sistema no log de auditoria.
  
**E se eu quiser que o administrador tenha controle total sobre o ciclo de vida de TMRs e não quiser dar aos usuários finais a capacidade de substituir a data de validade?**
  
É recomendável usar as políticas de retenção e/ou exclusão do S+C disponíveis como parte da SKU de conformidade do E5. Essa oferta é destinada a resolver questões legais administrativas e políticas complexas orientadas por SLA.

Esse recurso destina-se exclusivamente a um mecanismo leve de manutenção para reduzir a confusão de armazenamento criada a partir de TMRs frios.
  
**Quando o arquivo será excluído?**
  
O arquivo será excluído dentro de cinco dias a partir da data de validade, embora essa não seja uma garantia estrita.
  
**As TMRs futuras migrados do Fluxo Clássico após o lançamento desse recurso também terão a expiração automática aplicada a elas?**
  
Não, as TMRs migradas não virão com uma expiração definida. Em vez disso, incentivamos os administradores a migrar apenas as TMRs que desejam reter. Mais detalhes serão fornecidos na documentação de migração.
  
## <a name="manage-meeting-recordings"></a>Gerenciar gravações de reunião

As gravações de reunião são armazenadas como arquivos de vídeo no OneDrive for Business e no SharePoint Online e seguem as opções de gerenciamento e governança disponíveis nessas plataformas. Leia [visão geral de governança do SharePoint Online](/sharepoint/governance-overview), guia de [OneDrive for Business para empresas](/onedrive/plan-onedrive-enterprise)ou guia de [OneDrive for Business para pequenas empresas](/onedrive/one-drive-quickstart-small-business) para obter mais informações.

Para reuniões que não são de canal, as gravações são armazenadas no OneDrive for Business do gravador, manipulando a propriedade e a retenção depois que um funcionário sair seguirá o processo normal do [OneDrive for Business e do SharePoint Online](/onedrive/retention-and-deletion#the-onedrive-deletion-process).

## <a name="closed-captions-for-recordings"></a>Legendas ocultas para gravações

As legendas ocultas para gravações de reunião do Teams estarão disponíveis durante a reprodução somente se o usuário tiver ativado a transcrição no momento da gravação. Os administradores devem [ativar a transcrição da gravação por meio da política](#turn-on-or-turn-off-recording-transcription) para garantir que os usuários tenham a opção de gravar as reuniões com transcrição.

As legendas ajudam a criar conteúdo inclusivo para visualizadores de todas as habilidades. Como proprietário, você pode ocultar legendas na gravação da reunião, embora a transcrição da reunião ainda esteja disponível no Teams, a menos que você a exclua lá.

As legendas ocultas de hoje para o arquivo de vídeo de gravação estão vinculadas à transcrição da reunião do Microsoft Teams. Esse link permanecerá durante o tempo de vida do arquivo na maioria dos casos, mas poderá ser interrompido se o arquivo de vídeo for copiado no mesmo site do OneDrive for Business ou do Microsoft Office SharePoint Online, o que resultaria em legendas não disponíveis no arquivo de vídeo copiado.

Quaisquer alterações futuras no link entre a transcrição no Teams e a gravação serão esclarecidas aqui e nas notificações do centro de mensagens. Se fizermos alterações no futuro, garantiremos que os arquivos de gravação com menos de 60 dias exibam a transcrição da reunião como legendas.

> [!NOTE]
> A transcrição da reunião ainda não está disponível na GCC.

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>Descoberta Eletrônica e Conformidade para gravações de reunião

### <a name="ediscovery"></a>Descoberta Eletrônica

As gravações de reunião são armazenadas no OneDrive for Business e no SharePoint Online, que Microsoft 365 e em conformidade com o Office 365 Tier-D. Para dar suporte a solicitações de descoberta eletrônica para administradores de conformidade interessados em gravações de reunião ou chamada, a mensagem de gravação concluída está disponível na funcionalidade de pesquisa de conteúdo de conformidade do Microsoft Teams. Os administradores de conformidade podem procurar a palavra-chave "gravação" na linha do assunto do item na visualização de pesquisa de conteúdo de conformidade e descobrir as gravações da reunião e de chamadas na organização.

Além disso, o arquivo de vídeo de gravação de reunião pode ser encontrado por meio de pesquisas de Descoberta Eletrônica para arquivos no SharePoint Online e OneDrive for Business.

Para saber mais sobre a Descoberta Eletrônica, consulte o artigo [soluções de Descoberta Eletrônica para Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Políticas de retenção

Você pode aplicar rótulos de retenção automática para direcionar apenas arquivos de vídeo de gravação de reunião do Teams por meio da propriedade ProgID. Para obter mais informações, [como aplicar automaticamente um rótulo de retenção para gravações de reunião do Teams](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

### <a name="data-loss-prevention-dlp-policies"></a>Políticas DLP (Prevenção contra Perda de Dados)

Você pode aplicar políticas DLP a arquivos de gravação de reunião também pela propriedade ProgID. Na regra DLP para arquivos no SharePoint Online e OneDrive for Business defina as condições como:

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

2. No painel Executar diagnóstico, insira a URL da reunião no campo **URL da reunião que foi gravada** (geralmente encontrada no convite da reunião), e a data da reunião no campo **Quando a reunião foi gravada? ** e selecione **Executar Testes**.

3. Os testes validam se a gravação da reunião foi concluída com êxito e foi carregada no Stream ou no OneDrive.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
