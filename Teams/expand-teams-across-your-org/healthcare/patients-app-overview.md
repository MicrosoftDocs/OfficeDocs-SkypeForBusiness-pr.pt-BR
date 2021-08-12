---
title: 'Aplicativo Pacientes para administradores do Teams '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Saiba mais sobre o aplicativo Pacientes para administradores do Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 24b9813d14654b58018df5d26b94dc5afdaf816725b273c4a18c380bbd03552b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308740"
---
# <a name="patients-app-overview"></a>Visão geral do aplicativo Pacientes

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes será retirado e substituído pelo [aplicativo de Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio do grupo do Office 365 que apoia a equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas usando o [aplicativo Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Com o Lists, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam desde reuniões gerais com a equipe de atendimento até o monitoramento geral dos pacientes. Confira o modelo Pacientes no Lists para começar. Para saber mais sobre como gerenciar o aplicativo Lists em sua organização, consulte [Gerenciar o aplicativo Lists](../../manage-lists-app.md).

O aplicativo Pacientes é um aplicativo do repositório do Microsoft Teams disponível para todos os usuários do Teams. O aplicativo habilita equipes de saúde dos pacientes formadas por colaboradores clínicos (por exemplo, enfermeiros, médicos e assistentes sociais) possam selecionar e analisar listas de pacientes para cenários que variam de reuniões de equipes de turnos e reuniões de equipe a monitoramento geral dos pacientes.

O aplicativo tem dois modos:

- O modo Conectado do EMR que se conecta às EMRs por meio de FHIR. O aplicativo do modo Conectado à EMR permanece em visualização particular e os administradores ou clientes interessado podem solicitar acesso ao aplicativo enviando um email para Microsoft no [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) com informações sobre sua organização do Microsoft 365.
- O modo manual que permite às equipes de saúde adicionar/trazer manualmente as informações dos pacientes. O aplicativo está disponível na loja de aplicativos do Teams para que os usuários finais o baixem em visualização particular. O aplicativo pode ficar restrito a determinadas seções de usuários usando [políticas de configuração do aplicativo](../../teams-app-setup-policies.md) no Teams. Para obter acesso ao aplicativo, seu locatário precisa fazer parte do Programa de Adoção de Tecnologia (TAP). Envie-nos um email no [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) para iniciar o processo para solicitar acesso.

## <a name="usage-example"></a>Exemplo de uso

Durante as rodadas de sessões em cada turno em consultórios médicos, os médicos se reúnem no posto de enfermagem para discutir as atualizações mais recentes sobre o progresso com pacientes no consultório.  Eles destacam as principais métricas críticas (não necessariamente médicas ou que são explícitas sobre os registros médicos dos pacientes) e garantem que o paciente está no caminho certo para o diagnóstico com base no diagnóstico. Para contornar esses pacientes, a enfermeira responsável configura o aplicativo dos pacientes em uma equipe em que todos os profissionais são adicionados e adicionam pacientes a uma lista de pacientes. Durante as rodadas, os enfermeiros e outros profissionais de saúde responsáveis pelo acesso do paciente ao Microsoft Teams e ao aplicativo Pacientes em seus dispositivos móveis e atualização das informações relevantes dos pacientes nos dispositivos e, em seguida, todas as outras pessoas da equipe de saúde poderão ver essas atualizações e anotações e permanecer em sincronia. Duas vezes por dia, no início e no final de um turno, também há várias reuniões com a equipe multiuso para ir para a lista de pacientes e usar o aplicativo Pacientes para se expressar e compartilhar informações sobre cada paciente usando o aplicativo Pacientes em uma tela de exibição grande. Muitas vezes, determinados profissionais também podem discar para essas reuniões do Teams remotamente e ainda fazer parte da discussão.

## <a name="configure-patients-app"></a>Configurar o aplicativo Pacientes

Consulte [Gerenciar políticas de configuração de aplicativo em Microsoft Teams](../../teams-app-setup-policies.md) para habilitar o aplicativo Pacientes para sua organização.

Para saber mais sobre como seus usuários finais podem acessar e instalar o Aplicativo Pacientes para uma equipe que eles tenham ou gerenciam, consulte [Introdução ao Pacientes do Microsoft Teams](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Perguntas frequentes (FAQ)

**Onde os dados do aplicativo Pacientes são armazenados?**

Todos os dados inseridos pelos usuários finais no aplicativo Pacientes, incluindo o esquema de coluna/campo, os dados reais inseridos na lista e nos itens da lista (ou seja, pacientes) são armazenados na infraestrutura segura e compatível do Exchange Online. Todos os dados são armazenados na caixa de correio do grupo associada à equipe. Essa arquitetura permite que o Aplicativo Pacientes cumpra com facilidade a residência de dados, o suporte para a nuvem governamental (futuramente) e outros recursos de proteção de informações/conformidade, como o suporte à Descoberta eletrônica. O aplicativo Pacientes opera em um escopo de equipe. Você precisará instalar uma instância do aplicativo por equipe.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**Onde posso adquirir o Aplicativo Pacientes?**

Se o aplicativo Pacientes estiver habilitado para sua organização pelo administrador, qualquer usuário final poderá acessar a loja de aplicativos do Teams e adicionar o aplicativo Pacientes a uma equipe da qual ele é membro. Para saber mais, consulte [Gerenciar políticas de configuração de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md).

**Posso ter várias instâncias do aplicativo Pacientes em uma equipe porque é assim que funciona minha enfermaria/unidade?**

Atualmente, você só pode instalar uma instância do aplicativo Pacientes para uma determinada equipe e somente no canal geral. No entanto, dentro do aplicativo, várias listas podem ser criadas para lidar com cenários de multicanais ou isolamento/separação. Por padrão, todos os membros da equipe terão acesso à guia Pacientes no canal geral. 

**Posso exportar todos os dados do aplicativo Pacientes?**
Agora não, mas este recurso será apresentado em breve. 

**Como este aplicativo acomoda a PHI, existe auditoria para impedir o acesso não autorizado ou a conformidade com as regulamentações?**

Sim, existe. Cada ação na interface do usuário executada por um usuário do Microsoft Teams no aplicativo Pacientes é auditada e está disponível no centro de segurança e conformidade. Os detalhes são explicados no [Logs de auditoria do aplicativo Pacientes](patients-audit.md).

