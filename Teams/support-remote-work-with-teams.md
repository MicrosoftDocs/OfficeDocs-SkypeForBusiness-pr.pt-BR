---
title: Ofereça suporte a trabalhadores remotos usando o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: Use este guia para ajudar os funcionários remotos da sua organização a serem produtivos usando o Microsoft Teams, especialmente quando estiverem trabalhando em casa (WFH) em resposta à epidemia de COVID-19 (coronavírus).
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fbdb875896ca07402d699f1ca2a28770cb46ee2
ms.sourcegitcommit: ae65fb089d98665c4b26e0345bb96241fb893f0b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42342898"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>Ofereça suporte a trabalhadores remotos usando o Microsoft Teams

Use as práticas recomendadas neste artigo para oferecer suporte aos usuários que trabalham remotamente ou em casa.

## <a name="technical"></a>Técnico

1.  Certifique-se de que o [Teams esteja ativado para todos](assign-teams-licenses.md)
    
      - Veja [Teams Exploratory](teams-exploratory.md) ou [Teams gratuito](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c) para disponibilizar o Teams para todos em sua empresa.

      - Os funcionários remotos dependem muito das reuniões e das conferências de áudio. Se você ainda não distribuiu essas cargas de trabalho, confira [Reuniões e conferências no Teams](deploy-meetings-microsoft-teams-landing-page.md).

2.  Informe seus usuários sobre o Teams. Baixe o [Kit de Sucesso do Cliente do Teams](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) para obter apresentações, e-mails de exemplo, pôsteres e guias de introdução.


5.  Certifique-se de que seus funcionários tenham acesso a Internet e largura de banda adequados para o Teams. Use a orientação em [Preparo da rede da sua organização para o Teams](prepare-network.md) para saber como fazer isso.
    - A largura de banda limitada pode afetar a qualidade do áudio nas reuniões do Teams. Para garantir a melhor experiência de reunião com condições de pouca largura de banda, estimule os usuários a limitar o vídeo e a usar a PSTN para chamadas e áudio de reunião. 

    - Se você precisar de ajuda para solucionar problemas com a qualidade da chamada ou da reunião, siga as instruções em [Problema conhecido: discando para os IDs de conferência do Skype for Business/Teams](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids) na parte inferior deste artigo.

2.  [Envie links de treinamento](enduser-training.md) para ajudar seus funcionários a aproveitar ao máximo o Teams.
    
3. Leia nossos novos conteúdos sobre como trabalhar remotamente e compartilhe-os com seus usuários:
        
      - Blog do Teams (28 de fevereiro de 2020): [4 dicas para trabalhar em casa com o Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)

      - [Colaborar com o Office 365](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [Trabalhando remotamente com o Teams e o Office 365](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  Incentive todos a [Instalar](get-clients.md#mobile-clients) e usar o aplicativo móvel: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758) [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > Se você estiver na China, vá para [obter Teams para Android na China](get-teams-android-in-china.md)

4.  Equipe sua [assistência técnica](troubleshoot-installation.md) para lidar com consultas de usuários.


## <a name="communications"></a>Comunicações

Use o Teams para se manter em contato com seus funcionários:
- Modelos de aplicativo[Equipes de toda a organização](create-an-org-wide-team.md) e [Communicator da empresa](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator).
    
- Envie informações sobre as políticas de trabalho em casa e de saúde e segurança da sua organização.
    
- Use [Eventos ao vivo](teams-live-events/what-are-teams-live-events.md) para realizar reuniões e divulgação em toda a empresa. Torne qualquer reunião com mais de 250 participantes um evento ao vivo. 

## <a name="personal-considerations"></a>Considerações adicionais

Aqui estão algumas dicas para trabalhar corretamente em casa:

- Tenha um espaço de trabalho físico definido com boa iluminação e ergonomia apropriada.

- Defina os limites das suas horas de trabalho e compromissos, e use o [status de presença](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e) do Teams para indicar quando você está ausente.

- Defina claramente quando está trabalhando em home office, não transforme sua casa em um escritório em tempo integral.

- Levante e faça intervalos periodicamente. Dê uma volta, alongue-se e prepare um chá para você.

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>Problema conhecido: discagem no Skype for Business ou nas IDs de conferência de equipes

Veja a seguir um resumo de uma postagem de 7 de fevereiro de 2020 (MC203397):

A Microsoft está ciente de que alguns usuários na região da China estão enfrentando problemas para usar o Skype for Business ou as IDs de Conferência do Teams. Na maioria dos casos, esses problemas são externos aos sistemas sob o nosso controle. Frequentemente, o problema é com as operadoras de telefonia e de telefonia local. 

Recomendamos o seguinte se você estiver enfrentando problemas de videoconferência:

- Peça para o organizador ou para o organizador da reunião ligar para o seu telefone PSTN ou celular
- Participe da chamada ou da reunião a partir dos clientes móveis ou da área de trabalho, usando o VoIP

Se você precisar registrar um tíquete de suporte, inclua o seguinte:
    
- Hora exata da chamada
- Número da ponte de conferência discado
- Rede telefônica chamada
- Número de telefone do chamador
