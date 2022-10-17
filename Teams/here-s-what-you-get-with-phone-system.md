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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Saiba mais sobre os recursos, a disponibilidade e como planejar e configurar o Microsoft Phone System para sua empresa. '
ms.openlocfilehash: ccc931bd15e511903715ca328a142eb4da313dea
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584782"
---
# <a name="heres-what-you-get-with-phone-system"></a>Veja o que você obtém com o Sistema de Telefonia

Este artigo descreve os recursos do Sistema de Telefonia. Para obter mais informações sobre como usar o Sistema de Telefonia como sua substituição de PBX (Private Branch Exchange) e opções para se conectar à PSTN (Rede Telefônica Pública Comunada), consulte O que é o Sistema [de Telefonia](what-is-phone-system-in-office-365.md).

Os clientes estão disponíveis para PC, Mac e dispositivos móveis, que fornece recursos em dispositivos de tablets e celulares para computadores e telefones IP da área de trabalho. Para obter mais informações, consulte [Obter clientes do Microsoft Teams](get-clients.md).

 > [!Note]
> Para obter detalhes sobre os sistemas de telefonia do Teams em diferentes plataformas, consulte [os recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

Para usar os recursos do Sistema de Telefonia, sua organização deve ter uma licença do Sistema de Telefonia. Para obter mais informações sobre licenciamento, confira [Licenciamento de complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Lembre-se de que a maioria dos recursos exige que você atribua a licença do Sistema de Telefonia e verifique se os usuários estão "habilitados para voz". Para atribuir a licença, use [o cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) e defina o parâmetro **EnterpriseVoiceEnabled** como $true. Alguns recursos, como o atendedor automático de nuvem, não exigem que um usuário esteja habilitado para voz. As exceções são destacadas na tabela abaixo.
  
## <a name="phone-system-features"></a>Recursos do Sistema de Telefonia

O Sistema de Telefonia fornece os seguintes recursos.
  
|Recurso sistema de telefonia  |Descrição |
|:-----|:-----|
|[Atendedores automáticos de nuvem](what-are-phone-system-auto-attendants.md)  |Permite que você crie um sistema de menus que permite que chamadores externos e internos localizem e localizem ou transfira chamadas para usuários ou departamentos da empresa em sua organização.  <br/> Observe que os *usuários não precisam* ter a voz habilitada para receber chamadas do atendedor automático discar por nome, discar por pesquisa de diretório de número. Os *usuários* precisam ter a voz habilitada para receber chamadas das opções de menu atendedor automático. |
|[Filas de chamadas na nuvem](create-a-phone-system-call-queue.md) <br> |Permite configurar como as filas de chamadas são gerenciadas para sua organização: por exemplo, configurar saudações e músicas em espera, procurar o próximo agente de chamada disponível para lidar com a chamada e assim por diante.  <br/> Observe que os *usuários precisam* ter a voz habilitada para receber chamadas de uma fila de chamadas.|
|[Música de espera](music-on-hold.md) | Reproduz música padrão definida pelo serviço ou música personalizada carregada pelo administrador do locatário quando uma chamada externa da Rede Telefônica Pública Comuada (PSTN) é colocada em espera. Esse recurso funciona para chamadas PSTN para Teams de um para um, além de chamadas feitas em uma fila de chamadas. Esse recurso fornece paridade de notificação em espera com outras plataformas. |
|Responder/iniciar chamadas (por nome e número)   |Permite que os usuários atendam chamadas de entrada com um toque e faça chamadas de saída discando o número de telefone completo ou clicando em um nome no cliente.   |
|[Opções de encaminhamento de chamadas e anel simultâneo](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |Permite que os usuários configurem regras de encaminhamento para que as chamadas possam ir com elas em qualquer lugar ou chamadas possam ser encaminhadas para colegas ou para a caixa postal.   |
|[Recebimento e encaminhamento de chamadas em grupo](call-sharing-and-group-call-pickup.md)  | Permite que os usuários compartilhem chamadas de entrada com colegas para que os colegas possam responder a chamadas que ocorrem enquanto o usuário não está disponível. Menos interrupções para os destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como eles querem ser notificados de uma chamada compartilhada de entrada. |
|[Transferir uma chamada e uma transferência consultiva](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |Permite que os usuários transfira chamadas para outra pessoa. Ou, se eles precisam sair do escritório, mas quiserem continuar a conversa, podem transferir as chamadas do computador ou telefone IP para o celular.  <br/> Observe que os *usuários não precisam* ter a voz habilitada para receber chamadas transferidas de outro usuário. |
|[Transferir para a chamada no meio da caixa postal*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | Permite que os usuários transfira para a caixa postal durante uma chamada. |
|[Recuperação e estacionamento de chamadas](call-park-and-retrieve.md)   | Permite que os usuários coloquem uma chamada em espera no serviço do Teams na nuvem. Quando uma chamada é estacionada, o serviço gera um código exclusivo para recuperação de chamadas. O usuário que estacionou a chamada ou outra pessoa pode usar esse código e um aplicativo ou dispositivo com suporte para recuperar a chamada.  |
|Ligar para o número de telefone da pesquisa   | Permite que os usuários façam uma chamada na caixa de pesquisa usando o comando /call e especificando um nome ou um número.  |
|[ID do chamador](how-can-caller-id-be-used-in-your-organization.md)   |Chamadas de dentro da empresa exibem uma ID de chamador detalhada que extrai informações do diretório corporativo, mostrando a ID da imagem e o cargo em vez de apenas um número de telefone. Para chamadas de números de telefone externos, a ID do chamador, conforme fornecido pelo provedor de serviços de telefonia, é exibida. Se os números de telefone externos forem números secundários no diretório corporativo, as informações do diretório corporativo serão exibidas.   |
|Alternância de dispositivo   |Permite que os usuários reproduzam uma chamada ou reunião em outro dispositivo HID conectado ao Teams; por exemplo, alternando dos alto-falantes do computador para um fone de ouvido.    |
|Roteamento de chamadas baseado em presença  |Controla as comunicações de entrada com presença, permitindo que o usuário bloqueie toda a comunicação de entrada, exceto aquelas indicadas especificamente.   |
|[Teclado de discagem integrado](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | Permite que os usuários disquem por nome ou número em qualquer lugar na barra de pesquisa e no teclado de discagem, acelerando o processo de fazer chamadas de saída.  |
|Chamada federada   |Permite que os usuários se conectem, comuniquem e colaborem com segurança com usuários em locatários federados.   |
|[Fazer e receber uma chamada de vídeo](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | Se a conta do usuário estiver habilitada para chamadas de vídeo, o usuário poderá fazer chamadas de vídeo presenciais com seus contatos. Só precisam de uma câmera, alto-falantes e microfone do computador. Os usuários também poderão usar um fone de ouvido se o computador não tiver um dispositivo de áudio interno. |
|[Caixa Postal da Nuvem](set-up-phone-system-voicemail.md)  | Quando um usuário recebe uma caixa postal, ela é entregue à caixa de correio do Exchange como um email com a mensagem de voz como anexo. Os usuários podem ouvir suas mensagens em seu telefone de área de trabalho certificado e em todos os aplicativos teams ou Skype for Business aplicativos. O suporte para transcrição de caixa postal foi adicionado a partir de março de 2017 e está habilitado por padrão para todas as organizações e usuários. <br> Observe que os *usuários não precisam* de uma licença do Sistema de Telefonia *nem precisam* ter a voz habilitada para usar Caixa postal na Nuvem recursos.    |
|[Caixa postal na Nuvem configurações do usuário](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permite que os usuários definam suas configurações de cliente para saudações de caixa postal, regras de atendimento de chamadas e idioma de saudação, incluindo saudações de ausência temporária. <br> Observe que os *usuários não precisam* de uma licença do Sistema de Telefonia *nem precisam* ter a voz habilitada para usar Caixa postal na Nuvem recursos.  |
|[Toque secundário](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | Os usuários com vários dispositivos de alto-falante conectados ao computador podem optar por definir um dispositivo secundário para tocar além do alto-falante padrão. Por exemplo, um usuário com um fone de ouvido conectado ao computador e alto-falantes de mesa pode optar por ter o fone de ouvido e os alto-falantes de mesa anel quando uma chamada chega para que ele não perca uma chamada.  |
|[Alertas de anel distintos](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (somente Teams) |Permite que os usuários escolham toques separados para chamadas normais, chamadas encaminhadas e chamadas delegadas para que possam distinguir o tipo de chamada.   |
|[Aparência de linha compartilhada ](shared-line-appearance.md)  | Permite que os usuários compartilhem sua linha telefônica para que outro usuário possa fazer e receber chamadas em seu nome.|
|[Ocupado em Disponibilidade](teams-calling-policy.md) (somente Teams)  | Uma política de chamada que permite configurar como as chamadas de entrada são tratadas quando um usuário é: <ul><li>em uma chamada </li><li>em uma conferência</li><li>tem uma chamada colocada em espera. </li></ul> O chamador receberá uma das seguintes respostas: <ul><li>ouvir um sinal ocupado quando o receptor está no telefone</li> <li>será roteado de acordo com as configurações não respondidas do usuário. Uma opção permite que o chamador deixe uma caixa postal para o usuário que já está em uma chamada.</li></ul> O receptor recebe uma notificação de chamada perdida, mas não consegue atender chamadas recebidas. Esse recurso é desabilitado por padrão, mas pode ser ativado pelo administrador do locatário.|
|[Bloqueio de chamadas](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permite que os usuários adicionem números de telefone (PSTN) a uma lista bloqueada para que a próxima chamada desse número seja impedida de tocar no usuário.|
|[Telefones de área comuns](set-up-common-area-phones.md)  | Um telefone de área comum normalmente é colocado em uma área como um lobby ou sala de conferência, disponibilizando-o para várias pessoas. Os telefones de área comuns são configurados como dispositivos em vez de usuários e podem entrar automaticamente em uma rede.|
|[Suporte a bypass de mídia](direct-routing-plan-media-bypass.md) (somente para o Roteamento Direto do Teams)  | Para obter um melhor desempenho, a mídia é mantida entre o Controlador de Borda de Sessão (SBC) e o cliente em vez de enviá-la por meio do Sistema de Telefonia. |
|[Roteamento de número não atribuído](routing-calls-to-unassigned-numbers.md) | Permite o roteamento de números não atribuídos a usuários, atendedores automáticos, filas de chamadas ou um comunicado personalizado. |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilidade em nuvens GCC High e DoD
<a name="bkmk_setup"> </a>

Os recursos a seguir ainda não estão disponíveis nas nuvens GCC High e DoD. 

- [Configurações de chamada para toque secundário, caixa postal e delegação aprimorada](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transferir para a chamada no meio da caixa postal](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Ligar para o número de telefone da barra de pesquisa
- Música de espera
- Azure AD de número reverso

## <a name="related-topics"></a>Tópicos relacionados

- [O que é o Sistema de Telefonia](what-is-phone-system-in-office-365.md)
- [Voz na nuvem no Microsoft Teams](cloud-voice-landing-page.md)
- [Configurar o Sistema de Telefonia](setting-up-your-phone-system.md)
- [Qual plano de chamadas é ideal para você?](calling-plan-landing-page.md)
- [Monitorar e gerenciar a qualidade da chamada](monitor-call-quality-qos.md)
- [Licenciamento do complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Preços do sistema telefônico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams para Infraestrutura de Área de Trabalho Virtualizada com chamadas e reuniões](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
