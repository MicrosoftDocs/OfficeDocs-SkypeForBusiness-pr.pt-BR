---
title: Gravação de reuniões na nuvem do Microsoft Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: Orientações práticas para a implantação dos recursos de Cloud Voice no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9feaffd1677d96c53dee57b03f9061c6fa8184ce
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516936"
---
# <a name="teams-cloud-meeting-recording"></a>Gravação de reuniões na nuvem do Microsoft Teams

No Microsoft Teams, os usuários podem gravar suas reuniões de equipe e chamadas em grupo para capturar a atividade de compartilhamento de áudio, vídeo e tela. Há também uma opção para habilitar a transcrição automática nas gravações. Com isso, os usuários podem reproduzir gravações de reunião com legendas ocultas e procurar itens de discussão importantes na transcrição. A gravação ocorre na nuvem e é salva no [Microsoft Stream](https://docs.microsoft.com/stream/), para que os usuários possam compartilhá-lo com segurança em toda a organização.

Relacionados: [documentação do usuário final da gravação de reunião do teams](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Pré-requisitos para a gravação de reuniões na nuvem do teams

Para que as reuniões de um usuário do Team sejam gravadas, o Microsoft Stream deve ser habilitado para o locatário. Além disso, os pré-requisitos a seguir são necessários para o organizador da reunião e para a pessoa que está iniciando a gravação:

- O usuário tem um Office 365 E1, E3, e5, a1, a3, a5, M365, Business Premium ou fundamentos do negócio
- O usuário precisa estar licenciado para o Microsoft Stream<sup>1</sup> 
- O usuário tem permissões de vídeo de carregamento de fluxo da Microsoft
- O usuário consentiu nas diretrizes da empresa, se configurado pelo administrador
- O usuário tem armazenamento suficiente no Microsoft Stream para salvar gravações
- O usuário tem a configuração TeamsMeetingPolicy-AllowCloudRecording definida como true
- O usuário não é um usuário anônimo, convidado ou federado na reunião

> [!NOTE]
> Além disso, para permitir que a pessoa que inicia a gravação escolha se deseja transcrever automaticamente a gravação, a configuração TeamsMeetingPolicy-AllowTranscription do usuário deve ser definida como true

<sup>1</sup> O usuário precisa ser licenciado para carregar/baixar reuniões no Microsoft Stream, mas não precisa da licença para gravar uma reunião. Se você quiser impedir que um usuário grave uma reunião do Microsoft Teams, deverá conceder um TeamsMeetingPolicy que tenha AllowCloudRecording definido como $False.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar a gravação da reunião na nuvem do teams para usuários em sua organização

Esta seção explica como você pode configurar e planejar reuniões de equipes de gravação.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Habilitar o Microsoft Stream para usuários na organização

O Microsoft Stream está disponível como parte de assinaturas qualificadas do Office 365 ou como um serviço autônomo.  Consulte a [visão geral de licenciamento de fluxo](https://docs.microsoft.com/stream/license-overview) para obter mais detalhes.  O Microsoft Stream agora está incluído no Microsoft 365 Business, no Office 365 Business Premium e no Office 365 Business Essentials.

Saiba mais sobre como você pode [atribuir licenças a usuários no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários possam acessar o Microsoft Stream. Certifique-se de que o Microsoft Stream não seja bloqueado para os usuários, conforme definido neste [artigo](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Garantir que os usuários tenham permissões de vídeo de carregamento no Microsoft Stream

Por padrão, todos os participantes da empresa podem criar conteúdo no fluxo, uma vez que o fluxo está habilitado e a licença é atribuída ao usuário. Um administrador de fluxo da Microsoft pode [restringir funcionários para a criação de conteúdo](https://docs.microsoft.com/stream/restrict-uploaders) no Stream. Os usuários que estiverem nesta lista restrita não poderão gravar reuniões.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notificar os funcionários pelo consentimento para as diretrizes da empresa no Microsoft Stream

Se um administrador de fluxo [da Microsoft configurou a política de diretriz da empresa](https://docs.microsoft.com/stream/company-policy-and-consent) e requer que os funcionários aceitem essa política antes de salvar o conteúdo, os usuários devem fazer isso antes da gravação no Microsoft Teams. Antes de distribuir o recurso de gravação na organização, certifique-se de que os usuários consentiam na política.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Ativar ou desativar a gravação na nuvem

Use a configuração AllowCloudRecording no TeamsMeetingPolicy do teams PowerShell para controlar se as reuniões de um usuário podem ou não ser gravadas. Você pode saber mais sobre como gerenciar o TeamsMeetingPolicy com o PowerShell do Office 365 [aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Observe que o organizador da reunião e o iniciador de gravação precisam ter permissões de gravação para gravar a reunião. A menos que você tenha atribuído uma política personalizada aos usuários, os usuários obtêm uma política global, que tem o AllowTranscription desabilitado por padrão.

Para que um usuário retorne à política global, use o cmdlet a seguir para remover uma atribuição de política específica de um usuário:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para alterar o valor de AllowCloudRecording na política global, use o seguinte cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Cenário                                                                 |                                                                                                                                                                         Etapas                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Desejo que todos os usuários de minha empresa possam gravar suas reuniões                                    |                                                                     <ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = true<li>Todos os usuários têm o CsTeamsMeetingPolicy global ou uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = true </ol>                                                                     |
| Quero que a maioria dos meus usuários possa gravar suas reuniões, mas desabilitar seletivamente usuários específicos que não têm permissão para gravar |        <ol><li>Confirme que GlobalCsTeamsMeetingPolicy tem AllowCloudRecording = true<li>A maioria dos usuários tem o CsTeamsMeetingPolicy global ou uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = true<li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = false</ol>         |
|                                                   Eu quero que a gravação seja 100% desativada                                                   |                                                                <ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false<li>Todos os usuários receberam a CsTeamsMeetingPolicy global ou uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = falso                                                                 |
|      Desejo que a gravação seja desabilitada para a maioria dos usuários, mas habilitar seletivamente usuários específicos que têm permissão para gravar       | <ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false<li>A maioria dos usuários recebeu a CsTeamsMeetingPolicy global ou uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = false<li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = true <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="turn-on-or-turn-off-recording-transcription"></a>Ativar ou desativar a gravação da transcrição

Quando os usuários gravam suas reuniões de equipes, eles podem confirmar se uma transcrição deve ser gerada automaticamente após a reunião ser gravada. Se os administradores tiverem o recurso de transcrição desabilitado para o organizador da reunião e o iniciador de gravação, o iniciador de gravação não terá a opção de transcrever as gravações da reunião.

Use a configuração AllowTranscription no TeamsMeetingPolicy do teams PowerShell para controlar se um iniciador de gravação tem a opção de transcrever a gravação da reunião. Você pode saber mais sobre como gerenciar o TeamsMeetingPolicy com o PowerShell do Office 365 [aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

A menos que você tenha atribuído uma política personalizada aos usuários, ela obtém uma política global, que tem o AllowTranscription desabilitado por padrão.

Para que um usuário retorne à política global, use o cmdlet a seguir para remover uma atribuição de política específica de um usuário:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para alterar o valor de AllowCloudRecording na política global, use o seguinte cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Cenário|Etapas |
|---|---|
|Desejo que todos os usuários de minha empresa possam transcrever ao iniciar a gravação de uma reunião |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowTranscription = true <li>Todos os usuários têm o csTeamsMeetingPolicy global ou uma das políticas CsTeamsMeetingPolicy com AllowTranscription = verdadeiro. </ol>|
|Quero que a maioria dos meus usuários seja capaz de transcrever as gravações da reunião, mas desabilitar seletivamente usuários específicos que não têm permissão para transcrever |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowTranscription = true <li>A maioria dos usuários tem o CsTeamsMeetingPolicy global ou uma das políticas CsTeamsMeetingPolicy com AllowTranscription = true <li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com AllowTranscription = false </ol>|
|Desejo que a transcrição da gravação seja 100% desabilitada |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowTranscription = false <li>Todos os usuários receberam a CsTeamsMeetingPolicy global ou uma das políticas CsTeamsMeetingPolicy com AllowTranscription = falso </ol>|
|Quero desabilitar a transcrição para a maioria dos usuários, mas habilitar seletivamente usuários específicos que têm permissão para transcrever |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false <li>A maioria dos usuários recebeu a CsTeamsMeetingPolicy global ou uma das políticas CsTeamsMeetingPolicy com AllowCloudRecording = false <li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = true </ol>|
|||

### <a name="planning-for-storage"></a>Planejamento para armazenamento

O tamanho de uma gravação de 1 hora é de 400 MB. Certifique-se de compreender a capacidade necessária para arquivos registrados e ter armazenamento suficiente disponível no Microsoft Stream.  Leia [Este artigo](https://docs.microsoft.com/stream/license-overview) para entender o armazenamento base incluído na assinatura e como comprar armazenamento adicional.

## <a name="manage-meeting-recordings"></a>Gerenciar gravações de reunião
As gravações de reunião são consideradas conteúdo de Propriedade do locatário. Se o proprietário da gravação sair da empresa, o administrador poderá abrir a URL de vídeo de gravação no Microsoft Stream no modo de administração. O administrador pode excluir a gravação, atualizar todos os metadados de gravação ou alterar permissões para o vídeo de gravação. Saiba mais sobre os [recursos de administrador no Stream](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformidade e descoberta eletrônica para gravações de reunião
As gravações de reunião são armazenadas no Microsoft Stream, que é compatível com o nível C do Office 365. Para dar suporte a solicitações de descoberta eletrônica para administradores de conformidade que estejam interessados em reuniões ou chamadas de gravações para Microsoft streams, a mensagem de gravação concluída está disponível na funcionalidade de pesquisa de conteúdo de conformidade do Microsoft Teams. Os administradores de conformidade podem procurar a palavra-chave "gravando" na linha de assunto do item na visualização de pesquisa de conteúdo de conformidade e descobrir as gravações de reunião e de chamada na organização. Um pré-requisito para exibir todas as gravações é que elas precisarão ser configuradas no Microsoft Stream com acesso de administrador. Saiba mais sobre como [atribuir permissões de administrador no Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Configurar seu computador para o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

