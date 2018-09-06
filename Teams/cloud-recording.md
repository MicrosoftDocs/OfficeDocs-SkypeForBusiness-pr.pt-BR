---
title: Gravação de reunião de nuvem de equipes
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
description: Orientações práticas para a implantação dos recursos de Cloud Voice no Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c1ca0045eb980a83852426b9c0b2c12f1e317f0
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2018
ms.locfileid: "23845529"
---
# <a name="teams-cloud-meeting-recording"></a>Gravação de reunião de nuvem de equipes

> [!Note]
> [!INCLUDE [preview-feature](includes/preview-feature.md)]

No Teams da Microsoft, os usuários poderão gravar suas reuniões de equipes e chamadas de grupo para capturar áudio, vídeo e compartilhamento de atividade de tela. Há também uma opção de gravações ter transcrição automática, para que os usuários podem reproduzir gravações de reuniões com legendas e procurar itens de discussão importante na transcrição. A gravação acontece na nuvem e é salva no [Microsoft Stream](https://docs.microsoft.com/stream/), portanto, os usuários podem compartilhá-lo com segurança na sua organização.

[Documentação do usuário final de gravação de reunião de equipes](https://aka.ms/recordmeeting) de relacionados:

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Pré-requisitos para gravação de reunião de nuvem de equipes

Para reuniões do usuário equipes seja gravada, Microsoft Stream devem ser habilitado para o inquilino. Além disso, os seguintes pré-requisitos são necessários para o organizador da reunião e a pessoa que está iniciando a gravação:

- Usuário tem uma licença do Office 365 Enterprise E1, E3 ou E5
- O usuário precisa ser licenciados para o Microsoft Stream
- O usuário tem o Microsoft Stream carregar permissões de vídeos
- Usuário aceitou as diretrizes da empresa, se configurado pelo administrador
- Usuário tem armazenamento suficiente em Stream da Microsoft para gravações seja salvo
- Usuário tem TeamsMeetingPolicy-AllowCloudRecording configuração definida como true
- Usuário tem TeamsMeetingPolicy.AllowTranscription configuração definida como true, para que o usuário pode escolher se deseja transcrever automaticamente as gravações
- Usuário não é um anônimo, convidado ou usuário federado na reunião

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar a gravação de reunião de nuvem de equipes para usuários em sua organização

Esta seção explica como você pode configurar e planejar para reuniões de equipes de gravação.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Habilitar o Microsoft Stream para os usuários da organização

Microsoft Stream está disponível como parte das assinaturas do Office 365 elegíveis ou como um serviço autônomo.  Consulte a [Visão geral do fluxo de licenciamento](https://docs.microsoft.com/stream/license-overview) para obter mais detalhes.  Observe que a Microsoft Stream não está incluído no Business Essentials ou Business Premium planos.

Saiba mais sobre como você pode [Atribuir licenças aos usuários no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários podem acessar o Microsoft Stream. Certifique-se de que a Microsoft Stream não é bloqueado para os usuários, conforme definido [neste](https://docs.microsoft.com/stream/disable-user-organization)artigo.

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Certifique-se de que os usuários tenham carreguem permissões de vídeos no Microsoft Stream

Por padrão, todos na empresa podem criar conteúdo em Stream, depois que o Stream está habilitado e a licença é atribuída ao usuário. Um administrador do Microsoft Stream pode [restringir funcionários para a criação de conteúdo](https://docs.microsoft.com/stream/restrict-uploaders) no fluxo. Os usuários que estão nesta lista restritos não poderão gravar reuniões.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notificar os funcionários concorda com as diretrizes de empresa em Stream da Microsoft

Se um administrador do Microsoft Stream [Configurar a política de diretriz da empresa](https://docs.microsoft.com/stream/company-policy-and-consent) e requer funcionários aceitar essa política antes de salvar o conteúdo, os usuários devem fazer isso antes de gravação no Teams da Microsoft. Antes de você distribuir o recurso de gravação na organização, certifique-se de usuários têm consentiu à política.

### <a name="enabledisable-cloud-recording-for-users"></a>Habilitar/desabilitar nuvem para usuários de gravação

Use a configuração AllowCloudRecording no TeamsMeetingPolicy no PowerShell equipes para controlar se as reuniões de um usuário poderão ser registradas ou não. Saiba mais sobre como gerenciar TeamsMeetingPolicy com o Office 365 PowerShell [aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Observe que o organizador da reunião e o iniciador gravação precisam ter as permissões de gravação para gravar a reunião. A menos que você atribuiu uma política personalizada para os usuários, os usuários obtêm a política Global, que tem a gravação habilitada por padrão.

Para um usuário voltar a política Global, use o seguinte cmdlet para remover uma atribuição de política específicas de um usuário:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para alterar o valor de AllowCloudRecording na Política Global, use o seguinte cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|Cenário|Etapas |
|---|---|
|Desejo que todos os usuários da minha empresa possam registrar suas reuniões |<ol><li>Confirme CsTeamsMeetingPolicy Global tem AllowCloudRecording = True<li>Todos os usuários têm o Global OR CsTeamsMeetingPolicy uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = True </ol>|
|Desejo que a maioria dos meus usuários possam gravar suas reuniões, mas desabilitar seletivamente a usuários específicos que não são permitidos para registrar |<ol><li>Confirme GlobalCsTeamsMeetingPolicy tem AllowCloudRecording = True<li>A maioria dos usuários possuem o Global CsTeamsMeetingPolicy OR uma das diretivas de CsTeamsMeetingPolicy com AllowCloudRecording = True<li>Todos os outros usuários receberam uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = False</ol>|
|Deseja que a ser desabilitado 100% de gravação| <ol><li>Confirme CsTeamsMeetingPolicy Global tem AllowCloudRecording = False<li>Todos os usuários que tiverem sido concedidos a Global CsTeamsMeetingPolicy OR uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = False|
|Eu quero gravação para ser desabilitados para a maioria dos usuários, mas ativar seletivamente a usuários específicos que poderão gravar|<ol><li>Confirme CsTeamsMeetingPolicy Global tem AllowCloudRecording = False<li>A maioria dos usuários que tiverem sido concedidas a Global CsTeamsMeetingPolicy OR uma das diretivas de CsTeamsMeetingPolicy com AllowCloudRecording = False<li>Todos os outros usuários receberam uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = True <ol>|
|||

### <a name="enabledisable-recording-transcription-for-users"></a>Habilitar/desabilitar transcrições de gravação para usuários

Quando os usuários registrar suas reuniões de equipes, eles podem confirmar se uma transcrição deve ser gerada automaticamente após a reunião está registrada. Se os administradores tem desabilitado o recurso de transcrição para que o organizador da reunião e o iniciador de gravação, o iniciador de gravação não obterá uma opção transcrever as gravações de reuniões.

Use a configuração AllowTranscription no TeamsMeetingPolicy no PowerShell equipes para controlar se um iniciador de gravação obtém uma escolha transcrever a gravação de reunião. Saiba mais sobre como gerenciar TeamsMeetingPolicy com o Office 365 PowerShell [aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

A menos que você atribuiu uma política personalizada para os usuários, eles obtêm a política Global, que tiver desabilitado habilitada por padrão.

Para um usuário voltar a política Global, use o seguinte cmdlet para remover uma atribuição de política específicas de um usuário:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para alterar o valor de AllowCloudRecording na Política Global, use o seguinte cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Cenário|Etapas |
|---|---|
|Desejo que todos os usuários da minha empresa possam transcrever ao iniciar a gravação de uma reunião |<ol><li>Confirme CsTeamsMeetingPolicy Global tem AllowTranscription = True <li>Todos os usuários têm o csTeamsMeetingPolicy Global ou uma das diretivas de CsTeamsMeetingPolicy com AllowTranscription = True. </ol>|
|Desejo que a maioria dos meus usuários possam transcrever as gravações de reunião, mas desabilitar seletivamente a usuários específicos que não são permitidos transcrever |<ol><li>Confirme CsTeamsMeetingPolicy Global tem AllowTranscription = True <li>A maioria dos usuários possuem o Global CsTeamsMeetingPolicy OR uma das diretivas de CsTeamsMeetingPolicy com AllowTranscription = True <li>Todos os outros usuários receberam uma das políticas CsTeamsMeetingPolicy com AllowTranscription = False </ol>|
|Eu quero transcrição da gravação a ser desabilitado 100% |<ol><li>Confirme CsTeamsMeetingPolicy Global tem AllowTranscription = False <li>Todos os usuários que tiverem sido concedidos a Global CsTeamsMeetingPolicy OR uma das políticas CsTeamsMeetingPolicy com AllowTranscription = False </ol>|
|Eu quero transcrição ser desabilitados para a maioria dos usuários, mas permitir que usuários específicos que têm permissão para transcrever seletivamente |<ol><li>Confirme CsTeamsMeetingPolicy Global tem AllowCloudRecording = False <li>A maioria dos usuários que tiverem sido concedidas a Global CsTeamsMeetingPolicy OR uma das diretivas de CsTeamsMeetingPolicy com AllowCloudRecording = False <li>Todos os outros usuários receberam uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Planejando o armazenamento

O tamanho de uma gravação de 1 hora é 400 MB. Verifique se você compreende a capacidade necessária para os arquivos gravados e ter armazenamento suficiente disponível no Microsoft Stream.  Leia [Este artigo](https://docs.microsoft.com/stream/license-overview) entender o armazenamento base incluído na assinatura e como comprar armazenamento adicional.

## <a name="manage-meeting-recordings"></a>Gerenciar gravações de reuniões
As gravações de reunião são consideradas conteúdo pertencentes a locatário. Se o proprietário da gravação deixa a empresa, o administrador pode abrir a URL de vídeo de gravação em Microsoft Stream no modo de administrador. O administrador pode excluir a gravação, atualizar qualquer metadado de gravação ou alterar permissões para a gravação de vídeo. Saiba mais sobre [os recursos de administração no Stream](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformidade e eDiscovery para gravações da reunião
As gravações de reunião são armazenadas no Microsoft Stream, que é 365 Office camada-C compatível. Para oferecer suporte a solicitações de descoberta eletrônica para os administradores de conformidade que estiverem interessados em gravações de reunião ou chamada de Streams da Microsoft, a mensagem de gravação concluídas está disponível na funcionalidade de pesquisa de conteúdo de conformidade for Microsoft Teams. Administradores de conformidade podem procurar a palavra-chave "gravação" na linha de assunto do item na visualização da pesquisa de conteúdo de conformidade e descobrir reunião e os registros de chamada na organização. Um pré-requisito para que eles possam exibir todas as gravações é que eles precisam ser configurados no Microsoft Stream com acesso de administrador. Saiba mais sobre a [atribuição de permissões de administrador no fluxo](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Configurar seu computador para o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

