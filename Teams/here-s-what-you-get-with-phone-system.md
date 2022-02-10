---
title: Veja o que você obtém com o Sistema de Telefonia
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, roykuntz
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Saiba mais sobre os recursos, disponibilidade e como planejar e configurar o Telefone Microsoft System para sua empresa. '
ms.openlocfilehash: 3c641da9434745a9f349ad69171d7471090c1baf
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518913"
---
# <a name="heres-what-you-get-with-phone-system"></a>Veja o que você obtém com o Sistema de Telefonia

Este artigo descreve Sistema de Telefonia recursos. Para obter mais informações sobre como usar o Sistema de Telefonia como sua substituição de Exchange (PBX) e opções para se conectar à PSTN (Rede Telefônica Pública Comucionária), consulte [O](what-is-phone-system-in-office-365.md) que é Sistema de Telefonia.

Os clientes estão disponíveis para PC, Mac e dispositivos móveis, que fornece recursos em dispositivos de tablets e telefones celulares para computadores e telefones IP da área de trabalho. Para obter mais informações, consulte [Obter clientes para Microsoft Teams](get-clients.md).

 > [!Note]
> Para obter detalhes Teams sistemas de telefone em diferentes plataformas, [consulte Teams recursos por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

Para usar Sistema de Telefonia recursos, sua organização deve ter uma Sistema de Telefonia de usuário. Para obter mais informações sobre licenciamento, confira [Licenciamento de complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Esteja ciente de que a maioria dos recursos exige que você atribua a Sistema de Telefonia e verifique se os usuários estão "habilitados para voz". Para atribuir a licença, use o [cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) e desmarque o parâmetro **EnterpriseVoiceEnabled** como $true. Alguns recursos, como o atendimento automático na nuvem, não exigem que um usuário seja habilitado para voz. Exceções são chamadas na tabela abaixo.
  
## <a name="phone-system-features"></a>Sistema de Telefonia recursos

Sistema de Telefonia fornece os seguintes recursos.
  
|Sistema de Telefonia recurso  |Descrição |
|:-----|:-----|
|[Atendentes automáticos na nuvem](what-are-phone-system-auto-attendants.md)  |Permite que você crie um sistema de menus que permite que chamadores externos e internos localizem e façam ou transfira chamadas para usuários ou departamentos da empresa em sua organização.  <br/> Observe que os *usuários não precisam* ter voz habilitada para receber chamadas do atendimento automático discar por nome, discar por pesquisa de diretório de número. Os *usuários precisam* ter voz habilitada para receber chamadas das opções de menu de atendimento automático. |
|[Filas de chamada na nuvem](create-a-phone-system-call-queue.md) <br> |Permite configurar como as filas de chamada são gerenciadas para sua organização: por exemplo, configurar saudações e músicas em espera, procurar o próximo agente de chamada disponível para lidar com a chamada e assim por diante.  <br/> Observe que os *usuários precisam* estar habilitados para voz para receber chamadas de uma fila de chamadas.|
|[Música de espera](music-on-hold.md) | Reproduz músicas padrão definidas pelo serviço ou música personalizada carregada pelo administrador do locatário quando uma chamada externa da Rede Telefônica Pública Comuada (PSTN) é colocada em espera. Esse recurso funciona para chamadas PSTN para Teams, além de chamadas feitas para uma fila de chamadas. Esse recurso fornece paridade de notificação de espera com outras plataformas. |
|Responder/iniciar chamadas (por nome e número)   |Permite que os usuários atendam chamadas de entrada com um toque e faça chamadas de saída discando o número de telefone completo ou clicando em um nome no cliente.   |
|[Opções de encaminhamento de chamada e toque simultâneo](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |Permite que os usuários configurarem regras de encaminhamento para que as chamadas possam ir com elas para qualquer lugar, ou as chamadas podem ser encaminhadas para colegas ou para a caixa postal.   |
|[Retirada de chamada de grupo e encaminhamento para grupo](call-sharing-and-group-call-pickup.md)  | Permite que os usuários compartilhem chamadas de entrada com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário não está disponível. Menos prejudicial para destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como eles querem ser notificados de uma chamada compartilhada de entrada. |
|[Transferir uma chamada e transferência consultiva](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |Permite que os usuários transfira chamadas para outra pessoa. Ou, se precisarem sair do escritório, mas quiserem continuar a conversa, poderão transferir as chamadas do computador ou do telefone IP para o celular.  <br/> Observe que *os usuários não precisam* ter voz habilitada para receber chamadas transferidas de outro usuário. |
|[Transferir para a chamada no meio da caixa postal*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | Permite que os usuários transfira para a caixa postal durante uma chamada. |
|[Recuperação e estacionamento de chamadas](call-park-and-retrieve.md)   | Permite que os usuários coloquem uma chamada em espera no serviço Teams na nuvem. Quando uma chamada é estacionada, o serviço gera um código exclusivo para recuperação de chamada. O usuário que estacionou a chamada ou outra pessoa pode então usar esse código e um aplicativo ou dispositivo com suporte para recuperar a chamada.  |
|Número de telefone de chamada da pesquisa   | Permite que os usuários façam uma chamada da caixa de pesquisa usando o comando /call e especificando um nome ou um número.  |
|[ID do chamador](how-can-caller-id-be-used-in-your-organization.md)   |As chamadas de dentro da empresa exibem uma ID de chamador detalhada que tira informações do diretório corporativo, mostrando a ID da imagem e o cargo em vez de apenas um número de telefone. Para chamadas de números de telefone externos, a ID do chamador conforme fornecido pelo provedor de serviços telefônicos é exibida. Se os números de telefone externos são números secundários no diretório corporativo, as informações do diretório corporativo serão exibidas.   |
|Alternância de dispositivo   |Permite que os usuários reproduzam uma chamada ou reunião em outro dispositivo HID que esteja conectado a Teams; por exemplo, alternar de seus alto-falantes de computador para um fone de ouvido.    |
|Roteamento de chamadas baseadas em presença  |Controla as comunicações de entrada com presença, permitindo que o usuário bloqueie todas as comunicações de entrada, exceto aquelas especificamente indicadas.   |
|[Bloco de discagem integrado](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | Permite que os usuários discem por nome ou por número em qualquer lugar da barra de pesquisa e no bloco de discagem, acelerando o processo de fazer chamadas de saída.  |
|Chamada federada   |Permite que os usuários se conectem, se comuniquem e colaborem com usuários em locatários federados.   |
|[Fazer e receber uma chamada de vídeo](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | Se a conta do usuário estiver habilitada para chamadas de vídeo, o usuário poderá fazer chamadas de vídeo face a face com seus contatos. Só precisam de uma câmera, alto-falantes e microfone do computador. Os usuários também podem usar um fone de ouvido se o computador não tiver um dispositivo de áudio integrado. |
|[Caixa Postal da Nuvem](set-up-phone-system-voicemail.md)  | Quando um usuário recebe uma caixa postal, ela é entregue à caixa de correio Exchange como um email com a mensagem de caixa postal como um anexo. Os usuários podem ouvir suas mensagens em seu telefone de área de trabalho certificado e em todos os Teams ou Skype for Business aplicativos. O suporte para transcrição de caixa postal foi adicionado a partir de março de 2017 e está habilitado por padrão para todas as organizações e usuários. <br> Observe que *os usuários não precisam* de uma *Sistema de Telefonia, nem* precisam estar habilitados para voz para usar Caixa postal na Nuvem recursos.    |
|[Caixa postal na Nuvem configurações do usuário](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permite que os usuários configurem suas configurações de cliente para saudações de caixa postal, regras de atendimento de chamada e idioma de saudação, incluindo saudações fora do escritório. <br> Observe que *os usuários não precisam* de uma *Sistema de Telefonia, nem* precisam estar habilitados para voz para usar Caixa postal na Nuvem recursos.  |
|[Anelador secundário](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | Os usuários com vários dispositivos de alto-falante conectados ao computador podem optar por definir um dispositivo secundário para tocar, além do alto-falante padrão. Por exemplo, um usuário com um fone de ouvido conectado ao computador e alto-falantes de mesa pode optar por ter fones de ouvido e alto-falantes de mesa tocar quando uma chamada chegar para que ele não perca uma chamada.  |
|[Alertas de toque distintos](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (Teams somente) |Permite que os usuários escolham toques separados para chamadas normais, chamadas encaminhadas e chamadas delegadas para que possam distinguir o tipo de chamada.   |
|[Aparência de linha compartilhada ](shared-line-appearance.md)  | Permite que os usuários compartilhem suas linhas telefônicas para que outro usuário possa fazer e receber chamadas em seu nome.|
|[Ocupado no Ocupado](teams-calling-policy.md) (somente Teams)  | Uma política de chamada que permite configurar como as chamadas de entrada são tratadas quando um usuário é: <ul><li>em uma chamada </li><li>em uma conferência</li><li>tem uma chamada colocada em espera. </li></ul> O chamador receberá uma das seguintes respostas: <ul><li>ouvir um sinal de ocupado quando o chamador está no telefone</li> <li>será roteado de acordo com as configurações não respondidas do usuário. Uma opção permite que o chamador deixe uma caixa postal para o usuário que já está em uma chamada.</li></ul> O chamador recebe uma notificação de chamada perdida, mas não é capaz de atender chamadas de entrada. Esse recurso está desabilitado por padrão, mas pode ser ligado pelo administrador do locatário.|
|[Bloqueio de chamada](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permite que os usuários adicionem números de telefone (PSTN) a uma lista bloqueada para que a próxima chamada desse número seja impedida de tocar no usuário.|
|[Telefones de área comum](set-up-common-area-phones.md)  | Um telefone de área comum normalmente é colocado em uma área como um lobby ou sala de conferência, disponibilizando-o para várias pessoas. Os telefones de área comum são definidos como dispositivos em vez de usuários e podem entrar automaticamente em uma rede.|
|[Suporte a bypass de mídia](direct-routing-plan-media-bypass.md) (somente Teams roteamento direto)  | Para melhor desempenho, a mídia é mantida entre o Controlador de Borda de Sessão (SBC) e o cliente, em vez de enviá-la pelo Sistema de Telefonia. |
|[Roteamento de números não atribuídos](routing-calls-to-unassigned-numbers.md) | Permite o roteamento de números não atribuídos para usuários, atendimentos automáticos, filas de chamadas ou um anúncio personalizado. |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilidade em GCC nuvens Alta e DoD
<a name="bkmk_setup"> </a>

Os recursos a seguir ainda não estão disponíveis GCC Nuvens Altas e DoD. 

- [Configurações de chamada para toque secundário, caixa postal e delegação aprimorada](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transferir para a chamada no meio da caixa postal](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Número de telefone de chamada da barra de pesquisa
- Música de espera
- Azure AD reverse number lookup

## <a name="related-topics"></a>Tópicos relacionados

- [O que é o Sistema de Telefonia](what-is-phone-system-in-office-365.md)
- [Voz na nuvem no Microsoft Teams](cloud-voice-landing-page.md)
- [Configurar o Sistema de Telefonia](setting-up-your-phone-system.md)
- [Qual plano de chamadas é ideal para você?](calling-plan-landing-page.md)
- [Monitorar e gerenciar a qualidade da chamada](monitor-call-quality-qos.md)
- [Licenciamento do complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Preços do sistema telefônico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams infraestrutura de área de trabalho virtualizada com chamada e reuniões](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
