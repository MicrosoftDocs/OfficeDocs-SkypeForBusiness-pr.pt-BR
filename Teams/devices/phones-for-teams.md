---
title: Telefones para o Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Este artigo aborda a lista de telefones certificados para o Microsoft Teams e os recursos com suporte nos telefones certificados para o Microsoft Teams.
ms.openlocfilehash: b017e02b2d3d2bdc6b01886929d034abb6650384
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583950"
---
# <a name="phones-for-microsoft-teams"></a>Telefones para o Microsoft Teams

O Microsoft Teams é compatível com um portfólio de telefones de mesa para usuários que exigem uma experiência de telefone tradicional. Este artigo fornece uma visão geral completa de telefones de equipes e pode ajudar no planejamento, no fornecimento e no gerenciamento de telefones do Microsoft Teams como parte da solução de seu sistema telefônico da Microsoft. 

Para oferecer uma experiência de alta qualidade e confiabilidade do Microsoft Teams em telefones, estamos estabelecendo parcerias e trabalhando ativamente com o Yealink, o Crestron, o Lenovo, o Polycom e o AudioCodes para desenvolver e certificar um amplo portfólio de telefones de mesa e dispositivos de áudio de sala de conferência. Para obter as informações mais recentes e atualizadas sobre os dispositivos do Microsoft Teams, vá para o [Teams Marketplace](https://office.com/teamsdevices).

## <a name="features-supported-by-teams-phones"></a>Recursos compatíveis com telefones de equipes
Os telefones certificados pela equipe têm uma ampla variedade de recursos para ajudar os usuários a realizar seus trabalhos e ajudá-lo a gerenciar o uso deles. Aqui está um resumo dos recursos disponíveis em telefones certificados pela equipe:

- **Autenticação** Os telefones usam autenticação moderna para simplificar a conexão e melhorar a segurança. Os usuários podem entrar digitando o nome de usuário e a senha do telefone ou conectando-se a partir de outro dispositivo, como PC/smartphone.
- **Discagem rápida e histórico de chamadas** Os usuários têm acesso rápido a seus contatos, histórico de chamadas e correio de voz. Eles podem facilmente gerenciar seus contatos e entradas de discagem rápida do seu telefone.
- **Reuniões e chamadas** Os usuários podem ver seus cronogramas e ingressar em reuniões usando a junção com um só toque do teams.
- **Grupos de chamadas** Os agentes telefônicos que participam dos grupos de chamadas podem facilmente gerenciar a disponibilidade e aceitar ou recusar chamadas de entrada na fila de chamadas.
- **Delegação de usuário** Os assistentes executivos e administradores podem gerenciar os telefones dos seus executivos-intercepte as chamadas recebidas; Faça chamadas em nome do executivo; assuma as chamadas que o executivo colocou em espera; e monitorar se o executivo está em uma chamada, em espera e assim por diante.
- **Hot desk** Os usuários podem obter seus contatos, reuniões e outras preferências, bastando entrar em um telefone. Quando eles terminarem, poderão desconectar-se e deixar o telefone pronto para o próximo usuário.
- **Vídeo** Telefones com suporte a vídeo permitem que os usuários ingressem em conferências e videoconferências da mesma forma que estavam em seus computadores. Os usuários podem manter a privacidade usando o redimensionamento da câmera e o comutador mudo do microfone quando estiverem disponíveis.
- **Melhor juntos** Os telefones podem ser bloqueados e desbloqueados de uma maneira integrada quando conectados ao computador Windows com um cliente de desktop Teams de 64 bits.
- **Acessibilidade** Os telefones têm vários recursos de acessibilidade, como texto de alto contraste, para que seja mais fácil para qualquer pessoa usá-los.
- **Suporte a E911 dinâmico e aprimorado** Os usuários conectados que ligarem para o 911 verão a respectiva localização no telefone. 
    > [!IMPORTANT]
    > Se um telefone não estiver conectado, ou se não tiver uma conexão com a Internet, 911 chamadas não poderão ser feitas. Se isso acontecer, uma notificação será exibida no telefone.

Além dos recursos acima, você pode controlar quais recursos estão disponíveis dependendo do tipo de licença e da política telefônica atribuídas ao usuário que está entrando no telefone. Por exemplo, os usuários que se conectarem a um telefone com suas contas pessoais podem acessar toda a gama de recursos-chamadas, reuniões, correio de voz e assim por diante. As contas atribuídas a uma licença de telefone comum que se conectarem a um telefone, no entanto, podem apenas ter acesso a uma variedade limitada de recursos; o histórico de chamadas e as agendas de reunião podem não ser mantidos, por exemplo, para proteger a privacidade dos usuários.

## <a name="required-licenses"></a>Licenças necessárias

As licenças do Microsoft Teams podem ser compradas como parte das [assinaturas do microsoft 365 e do Office 365](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description). Para saber mais sobre as licenças necessárias para usar o Microsoft Teams em telefones, consulte [licenças do sistema telefônico](https://products.office.com/microsoft-teams/voice-calling)disponíveis.

Para obter mais informações sobre como obter o Microsoft Teams, confira [como faço para obter acesso ao Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-your-phones-via-intune"></a>Implantar seus telefones via Intune

### <a name="conditional-access"></a>Acesso condicional

O acesso condicional é um recurso do Azure Active Directory que o ajuda a garantir que os dispositivos que acessam os recursos do Office 365 sejam gerenciados corretamente e sejam seguros.  Se você aplicar políticas de acesso condicional ao serviço do Teams, os dispositivos Android (incluindo um telefone de equipe) que acessam as equipes do Access devem ser registrados no Intune e suas configurações precisam estar em conformidade com as políticas.  Se o dispositivo não estiver registrado no Intune ou se estiver registrado, mas suas configurações não atenderem às suas políticas, o acesso condicional impedirá um usuário de entrar ou usar o aplicativo Teams no dispositivo.

Geralmente, as políticas de conformidade definidas no Intune são atribuídas a grupos de usuários.  Isso significa que, se você atribuir uma política de conformidade Android ao user@contoso.com, essa política será aplicada igualmente ao smartphone Android e a qualquer dispositivo de equipe baseado em Android que o user@contoso.com entrar.

Se você usar o acesso condicional, o que requer que o registro do Intune seja imposto, em sua organização, há algumas coisas que você precisa configurar para ter uma inscrição bem-sucedida do Intune:

- **Licença do Intune** O usuário que estiver entrando no Microsoft Teams Phone deve ser licenciado para o Intune.  Desde que os telefones dos Microsoft Teams sejam conectados a uma conta de usuário que tenha uma licença válida do Intune, o telefone será automaticamente registrado no Microsoft Intune como parte do processo de entrada.
- **Configurar o Intune** Você deve ter uma configuração de locatário do Intune configurada corretamente para o registro do administrador do dispositivo Android.

### <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurar o Intune para registrar dispositivos baseados em Android do teams

Os dispositivos baseados em Android do teams são gerenciados pelo Intune via gerenciamento de administrador de dispositivo Android (DA). Para que os dispositivos possam ser registrados no Intune, há algumas etapas básicas a serem realizadas.  Se você já estiver gerenciando dispositivos com o Intune hoje, provavelmente já fez todas essas coisas.  Caso contrário, veja o que fazer:

1. Defina a autoridade MDM (gerenciamento de dispositivo móvel) do Intune.  Se você nunca usou o Intune antes, é preciso definir a autoridade de MDM antes de poder inscrever dispositivos. Para obter mais informações, consulte [definir a autoridade de gerenciamento de dispositivos móveis](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Esta é uma etapa única que deve ser realizada durante a criação de um novo locatário do Intune.
2. Habilite o registro do administrador do dispositivo Android. O dispositivo de equipes baseado em Android é gerenciado como dispositivos de administrador de dispositivos com o Intune.  O registro do administrador do dispositivo está desativado por padrão para locatários recém-criados.  Para obter mais informações, consulte [registro do administrador do dispositivo Android](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Atribuir licenças a usuários. Os usuários de dispositivos do teams que estão sendo registrados no Intune devem receber uma licença válida do Intune. Para obter mais informações, consulte [atribuir licenças aos usuários para que eles possam registrar dispositivos no Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Atribuir políticas de conformidade do administrador do dispositivo.  Crie uma política de conformidade do administrador de dispositivo Android e atribua-a ao grupo do Azure Active Directory que contém os usuários que entrarão nos dispositivos do teams. Para obter mais informações, consulte [usar políticas de conformidade para definir regras para os dispositivos que você gerencia com o Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="manage-your-phones"></a>Gerenciar seus telefones

Um administrador de locatários pode gerenciar e manter todos os dispositivos do teams atualizados por meio do centro de administração do teams. Para obter mais informações, consulte [gerenciar seus dispositivos no Microsoft Teams](https://docs.microsoft.com/microsoftteams/devices/device-management). 

## <a name="see-also"></a>Confira também

[Marketplace do teams](https://office.com/teamsdevices)

[Telefones IP certificados para o Microsoft Teams](teams-ip-phones.md)
