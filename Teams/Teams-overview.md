---
title: Visão geral do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Conheça o Microsoft Teams, sua infraestrutura e a utilização do Teams com o Office 365.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb291c8bd338fa88d5d9b5788413c5e687fc0864
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883775"
---
<a name="overview-of-microsoft-teams"></a>Visão geral do Microsoft Teams
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


O Microsoft Teams reúne toda a amplitude e a profundidade do Office 365 para oferecer um verdadeiro hub baseado em bate-papo para trabalhos em equipe e oferecer aos clientes a oportunidade de criar um ambiente mais aberto, fluido e digital. O Microsoft Teams é desenvolvido com as tecnologias existentes da Microsoft, reunidas aos grupos do Office 365. 

Fora da caixa, o Teams aproveita as identidades armazenadas no Azure Active Directory (Azure AD) e se integra aos outros serviços do Office 365 para criar um site online do SharePoint e uma caixa de correio de grupo do Exchange Online para cada equipe criada.

Qualquer pessoa com uma conta de email de consumidor ou de negócios, como o Outlook, Gmail ou outras pessoas, pode participar como um convidado em equipes. Todos os convidados em equipes são abordados pelo mesma conformidade e proteção de auditoria como o restante do Office 365 e convidados podem ser gerenciados com segurança dentro do Azure AD. Os administradores podem centralmente gerenciar como convidados que participam em seu ambiente do Office 365 e facilmente exibir, adicionar ou revogar o acesso do convidado ao inquilino host.

O Microsoft Teams oferece uma funcionalidade de chat persistente, chamadas e reuniões, acesso fácil a outros componentes do Office 365, além de um relato robusto de extensibilidade.  Isso proporciona um hub para o trabalho em equipe apropriado para grandes corporações, pequenas organizações e todas as empresas intermediárias.  

Para ampliar os recursos do Teams, use Conectores, Guias e Bots, disponíveis como [Aplicativos](https://go.microsoft.com/fwlink/?linkid=854629), para trazer informações externas, conteúdo e interações de bots inteligentes para o Teams.  

<a name="microsoft-teams-infrastructure"></a>Infraestrutura do Microsoft Teams
------------------------------

O Teams é desenvolvido com as tecnologias existentes da Microsoft, reunidas aos grupos do Office 365. Alimentado pela nuvem da Microsoft, as organizações podem esperar um excelente desempenho e confiabilidade ao aproveitar o Teams como parte da sua história de colaboração.

Fora da caixa, uma equipe criada no Teams criará um grupo do Office 365, um site do SharePoint Online (completo, com uma biblioteca de documentos) e uma caixa de correio de grupo do Exchange Online, que será usada pelo Teams ara armazenar informações, como convites de reunião. Uma equipe pode ser criada usando os Grupos existentes do Office 365, permitindo que as assinaturas de grupo existentes e os conteúdos armazenados no SharePoint Online e no Exchange Online sejam transferidos ao Teams.

Para complementar o recurso de equipes, como um quadro de bate-papo persistente onde conversas informais e em tempo real estas ocorrem, às equipes também fornece uma chamada e experiência criada da próxima geração baseado em nuvem de infra-estrutura que também é usada pelo Skype e Skype da reunião Negócios. Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade.

Os Grupos do Office 365 aproveitam as identidades armazenadas no Azure Active Directory (Azure AD) e, assim, todos os recursos de autenticação e autorização do Azure AD, como suporte para autenticação multifator (MFA), estão prontamente disponíveis para uso no Teams.

> [!NOTE]
> Com base nos comentários do cliente, novos grupos de Office 365 gerado como resultado de criação de uma equipe no Microsoft Teams não mais aparecerá no Outlook por padrão. Para clientes que deseja continuar com o comportamento existente do mostrando esses grupos no Outlook, um cmdlet do PowerShell do Exchange Online será fornecido que pode permitir que o grupo para a experiência do Outlook. Grupos criados pelo Outlook e habilitado mais tarde para equipes continuará Mostrar no Outlook e equipes. Essa atualização será gradualmente roll a saída entre o Outlook e as equipes nos próximos meses.


<a name="microsoft-teams-and-office-365"></a>Microsoft Teams e Office 365
------------------------------

Os diferentes grupos têm necessidades variadas com base no seu papel funcional e estilo de trabalho. O Office 365 foi projetado para o estilo de trabalho exclusivo de cada grupo e inclui aplicativos integrados e específicos para o propósito, incluindo:

-   Outlook para e-mails profissionais, agora com a funcionalidade de grupos

-   SharePoint para sites e portais, serviços de conteúdo inteligente, automação de processos comerciais e pesquisa empresarial

-   Yammer para impulsionar as conexões em toda a empresa

-   Skype for Business como o suporte principal de voz e vídeos empresariais

-   E agora, p Microsoft Teams, o novo espaço de trabalho baseado em bate-papo do Office 365

Seguem alguns casos de uso comuns de cada aplicativo do Office 365. Para obter orientações de uso detalhadas, acesse a [Biblioteca de Produtividade FastTrack](https://go.microsoft.com/fwlink/?linkid=854630).

![Ícone do Microsoft Teams.](media/Overview_of_Microsoft_Teams_image1.png)

-   Aproveitado por usuários e equipes que desejam colaborar em tempo real com o mesmo grupo de pessoas.

-   Ajuda as equipes que desejam iterar rapidamente em um projeto, enquanto compartilham arquivos e colaboram em materiais compartilhados.

-   Permite que os usuários se conectem a uma ampla variedade de ferramentas na sua área de trabalho (por exemplo, planejador, Power BI, GitHub, etc.).

![Ícone do Microsoft Outlook.](media/Overview_of_Microsoft_Teams_image2.png)

-   Aproveitado por usuários que preferem colaborar no ambiente familiar de e-mails e/ou de uma forma mais formal e estruturada.

-   Fornece processos comerciais específicos que exigem o uso de e-mails para transferir documentos e informações dentro e fora dos limites corporativos.

-   Comunica e se conecta com usuários que estão fora de grupos de trabalho ou organizações imediatos.

![Ícone do Yammer.](media/Overview_of_Microsoft_Teams_image3.png)

-   Aproveitado para ajudar a conectar usuários em toda a organização para se organizarem em comunidades de prática e compartilharem boas práticas.

-   Melhora os fluxos de trabalho multifuncionais através de uma plataforma aberta e transparente baseada em feed

-   Promove o envolvimento entre executivos e funcionários através de conversas bidirecionais entre a liderança e a base mais ampla de funcionários

-   Incentiva sua força de trabalho da linha de frente a compartilhar e receber conhecimentos e expertise

![Ícone do Skype for Business.](media/Overview_of_Microsoft_Teams_image4.png)

-   Aproveitado para comunicação e colaboração em tempo real, interna e externamente com clientes/parceiros.

-   Proporciona reuniões com áudio, vídeo e conteúdo, com equipes grandes ou pequenas (incluindo assembleias com até 10.000 participantes).

-   Oferece funcionalidade de telefonia corporativa.


![Ícone do Microsoft SharePoint.](media/Overview_of_Microsoft_Teams_image5.png)

-   Aproveitado para sites e portais (ex.: notícias e anúncios de empresas, pesquisa e colaboração de documentos).

-   Implementa a automação de processos comerciais em bibliotecas de documentos e listas de informações, integrando o Microsoft Flow e o PowerApps.

-   O site SharePoint da equipe totalmente alimentado é provisionado para cada equipe do Microsoft Teams para armazenamento de arquivos, notícias da equipe, páginas, listas e muito mais.

-   Consulte [Como o SharePoint Online e o OneDrive for Business interagem com o Teams](SharePoint-OneDrive-interact.md)

## <a name="teams-known-issuesknown-issuesmd"></a>[Problemas conhecidos do Teams](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[Notas de versão do cliente Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)


