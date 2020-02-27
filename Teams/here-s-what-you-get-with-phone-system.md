---
title: Veja aqui o que você obtém com o Sistema de Telefonia no Office 365
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Saiba mais sobre os recursos, a disponibilidade e a forma de planejar e configurar o sistema telefônico da Microsoft para sua empresa. '
ms.openlocfilehash: 27ec4803a33f524d1c260c27c1af3c71210b33d2
ms.sourcegitcommit: 152eb7daacd0a36f42aa441633c12c7037a0969a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288699"
---
# <a name="heres-what-you-get-with-phone-system-in-office-365"></a>Veja aqui o que você obtém com o Sistema de Telefonia no Office 365

Este artigo descreve o sistema telefônico nos recursos do Office 365. Para obter mais informações sobre como usar o sistema telefônico como a substituição de PBX (Private Branch Exchange) e opções para conexão à rede telefônica pública comutada (PSTN), consulte [o que é o sistema telefônico no Office 365](what-is-phone-system-in-office-365.md).

Os clientes estão disponíveis para PC, Mac e celular, que fornece recursos para dispositivos de tablets e celulares para PCs e telefones IP de área de trabalho. Para obter mais informações, consulte [obter clientes para Microsoft Teams](get-clients.md).

  
## <a name="phone-system-in-office-365-features"></a>Sistema telefônico nos recursos do Office 365

O sistema de telefonia fornece os recursos a seguir. A menos que indicado de outra forma, os recursos estão disponíveis no Teams e no Skype for Business online.
  
|||
|:-----|:-----|
|**Sistema telefônico no recurso Office 365** <br/> |**Descrição** <br/> |
|[Atendedores automáticos da nuvem](what-are-phone-system-auto-attendants.md) <br/> |Permite criar um sistema de menus que permite que chamadores externos e externos localizem e façam ou transfiram chamadas para usuários ou departamentos da empresa em sua organização.  <br/> |
|[Filas de chamadas na nuvem](create-a-phone-system-call-queue.md) <br/> |Permite configurar como as filas de chamadas são gerenciadas para sua organização: por exemplo, configurar saudações e músicas em espera, procure o próximo agente de chamada disponível para lidar com a chamada e assim por diante.  <br/> |
|Música de espera | Reproduz a música padrão definida pelo serviço quando uma chamada externa da PSTN (rede telefônica pública comutada) é colocada em espera. Esse recurso funciona para chamadas PSTN-to-Team de um para um, além de chamadas feitas para uma fila de chamadas. Esse recurso fornece a paridade de notificação em espera com outras plataformas. Esse recurso é configurável pelo administrador, mas [atualmente apenas pelo PowerShell](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Também não há suporte para a música em uma transferência consultiva de uma chamada PSTN.|
|Responder/iniciar chamadas (por nome e número)  <br/> |Permite que os usuários respondam a chamadas de entrada com um toque e façam chamadas de saída, discando o número de telefone completo ou clicando em um nome no cliente.  <br/> |
|[Opções de encaminhamento de chamadas e toque simultâneo](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Permite que os usuários configurem regras de encaminhamento para que as chamadas possam entrar em qualquer lugar, ou as chamadas podem ser encaminhadas para colegas ou para correio de voz.  <br/> |
|[Atendimento de chamada em grupo e encaminhar para grupo](call-sharing-and-group-call-pickup.md) <br/> | Permite que os usuários compartilhem chamadas com colegas para que os colegas possam atender chamadas que ocorrem enquanto o usuário está indisponível. Menos interrupções nos destinatários do que outras formas de compartilhamento de chamadas (como encaminhamento de chamadas ou toque simultâneo) porque os usuários podem configurar como querem ser notificados sobre uma chamada compartilhada recebida. |
|[Transferir uma chamada e transferência consultiva](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Permite que os usuários Transfira chamadas para outra pessoa. Ou, se precisar sair do escritório, mas quiser continuar a conversa, eles podem transferir as chamadas de seu PC ou telefone IP para o telefone celular.  <br/> |
|[Transferir para a chamada intermediária do correio de voz](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Permite que os usuários transfiram para o correio de voz durante uma chamada. |
|[Recuperação e estacionamento de chamadas](call-park-and-retrieve.md)  <br/> | Permite que os usuários façam uma chamada em espera no serviço do teams na nuvem. Quando uma chamada está estacionada, o serviço gera um código exclusivo para recuperação de chamadas. O usuário que estacionau a chamada ou outra pessoa pode usar esse código e um aplicativo ou dispositivo com suporte para recuperar a chamada. <br/> |
|Ligar para o número de telefone da pesquisa  <br/> | Permite que os usuários façam uma chamada a partir da caixa de pesquisa usando o comando/Call e especificando um nome ou um número. <br/> |
|[ID do chamador](how-can-caller-id-be-used-in-your-organization.md)  <br/> |As chamadas de dentro da empresa exibem um identificador de chamadas detalhado que obtém informações do diretório corporativo, mostrando a ID da imagem e o cargo do trabalho em vez de apenas um número de telefone. Para chamadas de números de telefone externos, a identificação de chamadas fornecida pelo provedor de serviços de telefonia é exibida. Se os números de telefone externos forem números secundários do diretório corporativo, as informações do diretório corporativo serão exibidas.  <br/> |
|Alternância de dispositivo  <br/> |Permite que os usuários reproduzam uma chamada ou reunião em outro dispositivo HID conectado ao Teams; por exemplo, mudar de seus alto-falantes do PC para um fone de ouvido com microfone.   <br/> |
|Encaminhamento de chamadas baseado em presença <br/> |Controla comunicações de entrada com presença, permitindo que o usuário bloqueie toda a comunicação recebida, exceto aquelas indicadas especificamente.  <br/> |
|[Teclado de discagem integrado](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Permite que os usuários disquem por nome ou por número em qualquer lugar na barra de pesquisa e no teclado de discagem, acelerando o processo de fazer chamadas de saída. <br/> |
|Chamadas federadas  <br/> |Permite que os usuários se conectem, se comuniquem e colaborem com usuários em locatários federados.  <br/> |
|[Fazer e receber uma chamada de vídeo](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Se a conta do usuário estiver habilitada para chamadas com vídeo, o usuário poderá fazer chamadas com vídeo cara a cara com seus contatos. Basta usar uma câmera, os alto-falantes e o microfone do computador. Os usuários também podem usar um fone de ouvido com microfone se o computador não tiver um dispositivo de áudio embutido.<br/> |
|[Correio de voz na nuvem](set-up-phone-system-voicemail.md) <br/> | Quando um usuário recebe um correio de voz, ele é entregue à sua caixa de correio do Exchange como um email com a mensagem de correio de voz como um anexo. Os usuários podem ouvir suas mensagens em seu telefone de mesa certificado e em todas as equipes ou aplicativos Skype for Business. O suporte para a transcrição de correio de voz foi adicionado a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários.   <br/> |
|[Configurações do usuário da nuvem de correio de voz](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permite que os usuários configurem suas configurações de cliente para saudações de correio de voz, regras de atendimento de chamadas e idioma de saudação, incluindo mensagens de ausência temporária.   |
|[Toque secundário](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Os usuários com vários dispositivos de alto-falantes conectados ao PC podem optar por definir um dispositivo secundário para tocar além do alto-falante padrão. Por exemplo, um usuário com fone de ouvido conectado aos alto-falantes do computador e da mesa pode optar por usar o fone de ouvido com microfone e escrivaninha quando uma chamada chega para que ela não perca uma chamada.  |
|[Alertas de toque distintos](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (somente para equipes)<br/> |Permite que os usuários escolham toques separados para chamadas normais, chamadas encaminhadas e chamadas delegadas para que possam distinguir o tipo de chamada.  <br/> |
|[Aparência de linha compartilhada ](shared-line-appearance.md) <br/> | Permite que os usuários compartilhem a linha telefônica para que outro usuário possa fazer e receber chamadas em seu nome.|
|[Ocupado em ocupado](teams-calling-policy.md) (somente para equipes) <br/> | Uma política de chamada que permite que você configure como as chamadas de entrada são manipuladas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera. O chamador ouvirá um sinal de ocupado quando o receptor já estiver no telefone. O chamador obtém uma notificação de chamada perdida, mas não pode atender chamadas recebidas. Esse recurso está desabilitado por padrão, mas pode ser ativado pelo administrador do locatário. |
|[Bloqueio de chamadas](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permite que os usuários adicionem números de telefone de rede (PSTN) a uma lista bloqueada para que a próxima chamada desse número seja bloqueada de tocar o usuário.|
|[Telefones fixos de área comuns](set-up-common-area-phones.md) <br/> | Um telefone de área comum geralmente é colocado em uma área, como um lobby ou uma sala de conferência, tornando-o disponível para várias pessoas. Os telefones de área comuns são configurados como dispositivos, e não usuários, e podem entrar automaticamente em uma rede.|
|[Suporte à bypass de mídia](direct-routing-plan-media-bypass.md) (somente para roteamento direto do Teams) <br/> | Para obter melhor desempenho, a mídia é mantida entre o controlador de borda de sessão (SBC) e o cliente, em vez de enviá-lo por meio do sistema telefônico da Microsoft. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilidade em nuvens de GCC alta e DoD
<a name="bkmk_setup"> </a>

Os recursos a seguir ainda não estão disponíveis em nuvens de GCC alta e DoD. 
- [Configurações de chamada para toque secundário, correio de voz e delegação aprimorada](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transferir para a chamada intermediária do correio de voz](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Ligar para o número de telefone da barra de pesquisa
- Música de espera
- Pesquisa de número reverso do Azure AD

## <a name="related-topics"></a>Tópicos relacionados

- [O que é o sistema telefônico no Office 365](what-is-phone-system-in-office-365.md)
- [Voz na nuvem no Microsoft Teams](cloud-voice-landing-page.md)
- [Configurar o Sistema de Telefonia](setting-up-your-phone-system.md)
- [Qual plano de chamadas é ideal para você?](calling-plan-landing-page.md)
- [Roteamento Direto do Sistema Telefônico](direct-routing-landing-page.md)
- [Monitorar e gerenciar a qualidade da chamada](monitor-call-quality-qos.md)
- [Licenciamento do complemento do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Preço do sistema telefônico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams para infraestrutura de área de trabalho virtualizada com chamadas e reuniões](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
 
