---
title: Gerenciar o aplicativo Turnos para sua organização
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Saiba como configurar e gerenciar o aplicativo Shifts no Teams para trabalhadores de linha de frente em sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 358a0078eed6f693922b3aaedb3eea38a8bb7f82
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655857"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gerencie o aplicativo Turnos para sua organização no Microsoft Teams

## <a name="overview-of-shifts"></a>Visão geral do Turnos

O aplicativo Shifts no Microsoft Teams mantém os trabalhadores da linha de frente conectados e em sincronização. Ele foi criado primeiro para gerenciamento de tempo e comunicação rápido e eficaz para equipes. Os turnos permitem que os trabalhadores da linha de frente e seus gerentes usem seus dispositivos móveis para gerenciar agendas e manter contato.

- Os gerentes criam, atualizam e gerenciam cronogramas de turnos da equipe. Eles também podem enviar mensagens para uma pessoa ("há um derramamento no chão") ou para toda a equipe ("o gerente regional chega em 20 minutos"). Eles podem enviar documentos de política, boletins de notícias e vídeos.
- Os funcionários visualizam os próximos turnos rapidamente, podem ver quem mais está agendado para o dia, solicitar uma troca de turno, oferecer um turno e solicitar folgas.

É importante saber que o Shifts atualmente não dá suporte aos convidados. Isso significa que os convidados em uma equipe não podem ser adicionados ou usar escalas de turnos quando o acesso de Convidado estiver ativado no Teams.

> [!Note]
> Para obter detalhes sobre os recursos do Turnos em diferentes plataformas, confira [Recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilidade de Turnos

O Turnos está disponível em todas as SKUs corporativas onde o Teams está disponível.

> [!NOTE]
> Os turnos estão disponíveis em ambientes de GCC (Nuvem da Comunidade Governamental), mas não em ambientes GCC High ou DoD.

## <a name="location-of-shifts-data"></a>Local dos dados de Turnos

Atualmente, os dados de turnos são armazenados no Azure em data centers na Ásia-Pacífico (APAC), na União Europeia (UE) e América do Norte. Confira mais informações sobre onde os dados são armazenados em [Onde estão meus dados?](http://o365datacentermap.azurewebsites.net/)

Para saber mais sobre os dados shifts, incluindo armazenamento, retenção, recuperação e criptografia de dados Shifts, consulte [Perguntas frequentes sobre dados do Shifts](shifts-data-faq.md).

## <a name="set-up-shifts"></a>Configurar Turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar ou desabilitar o Turnos em sua organização

O Turnos é habilitado por padrão para todos os usuários do Teams em sua organização. Você pode desativar ou ativar o aplicativo no nível da organização na página [Gerenciar aplicativos](../../manage-apps.md) no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Na lista de aplicativos, pesquise o aplicativo Shifts, selecione-o e alterne o **alternância Status** para **Bloqueado** ou **Permitido**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilite ou desabilite o Turnos para usuários específicos em sua organização

Para permitir ou bloquear usuários específicos em sua organização de usar o Shifts, verifique se o Shifts está ativado para sua organização na página [Gerenciar aplicativos](../../manage-apps.md) . Em seguida, crie uma política personalizada para permissões de aplicativo e atribua-a a esses usuários. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](../../teams-app-permission-policies.md).

### <a name="pin-shifts-to-teams"></a>Fixar turnos para o Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>Usar a experiência de aplicativo de linha de frente personalizada para fixar Shifts e outros aplicativos no Teams

A experiência de aplicativo de linha de frente personalizada no Teams fixa os aplicativos mais relevantes no Teams para usuários que têm uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Os aplicativos fixados incluem Shifts, Walkie Talkie, Tarefas e Aprovações. Por padrão, esse recurso está ativado, dando aos seus trabalhadores de linha de frente uma experiência fora da caixa que é adaptada às suas necessidades.

Os aplicativos são fixados na barra de aplicativos , a barra na lateral do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, onde os usuários podem acessá-los rapidamente e facilmente.

Para saber mais, incluindo como a experiência funciona com políticas de aplicativo definidas, confira [Adaptar aplicativos do Teams para seus trabalhadores de linha de frente](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Usar uma política de configuração de aplicativo para fixar Shifts no Teams

As políticas de configuração do aplicativo permitem personalizar o Teams para fixar os aplicativos mais importantes para seus usuários.

Você pode criar uma [política personalizada na política de instalação do aplicativo](../../teams-app-setup-policies.md) adicionando o aplicativo Shifts e [atribuir a política](../../assign-policies-users-and-groups.md) aos usuários. Ou você pode usar a política de configuração do aplicativo que faz parte dos pacotes de política do Frontline Worker e do Frontline Manager.

Um [pacote de políticas](../../manage-policy-packages.md) no Teams é uma coleção de políticas e configurações de política predefinidas que você pode atribuir aos usuários que têm funções semelhantes em sua organização. O conjunto de políticas nos pacotes de política do Frontline Worker e do Frontline Manager inclui uma política de configuração de aplicativo que fixa o aplicativo Shifts e outros aplicativos que dão suporte a atividades de comunicação e colaboração para essa função.

Recomendamos usar os pacotes de política do Frontline Worker e do Frontline Manager à medida que eles simplificam, simplificam e ajudam a fornecer consistência ao gerenciar políticas para sua força de trabalho de linha de frente.

### <a name="enable-shift-based-tags-in-teams"></a>Habilitar marcas baseadas em turnos no Teams

[As marcas](https://support.microsoft.com/office/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e) no Teams permitem que os usuários se conectem facilmente com um subconjunto de pessoas em uma equipe. Com marcas baseadas em turnos, as pessoas recebem automaticamente marcas que correspondem à agenda e ao nome do grupo de turnos em Turnos. A marca pode ser usada em @mentions na linha **Para** em um chat ou em uma postagem em qualquer canal padrão da equipe.

As marcas baseadas em turno permitem que seus usuários alcancem pessoas que estão em turno em tempo real. As notificações são enviadas apenas para aquelas pessoas que estão em turno no momento em que a marca é usada em um chat ou postagem de canal. Por exemplo:

- Um gerente de loja usa a marca @Cashiers para postar um anúncio em um canal para todos os caixas em turno.
- Uma enfermeira usa a marca @CardiologistsOnCall para iniciar um bate-papo com todos os cardiologistas de plantão.

Você pode ativar ou desativar o recurso no centro de administração do Microsoft Teams. Para saber mais, confira [Gerenciar marcações no Teams](../../manage-tags.md).

## <a name="search-the-audit-log-for-shifts-events"></a>Pesquisar o registro de auditoria para eventos do Turnos

**(Na versão prévia)**

Você pode pesquisar no log de auditoria para exibir as atividades de Turnos na sua organização.  Para saber mais sobre como pesquisar no log de auditoria e ver uma lista de [atividades de Turnos](../../audit-log-events.md#shifts-in-teams-activities) que são registradas no log de auditoria, consulte [Pesquisar no log de auditoria por eventos no Teams](../../audit-log-events.md).

Para examinar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://protection.office.com). Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="related-articles"></a>Artigos relacionados

- [Turnos do Teams](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [Muda perguntas frequentes sobre dados](shifts-data-faq.md)
- [Conectores de turnos](/microsoft-365/frontline/shifts-connectors)
- [Ajuda de turnos para trabalhadores de linha de frente](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Atribua políticas a seus usuários no Teams](../../policy-assignment-overview.md)
