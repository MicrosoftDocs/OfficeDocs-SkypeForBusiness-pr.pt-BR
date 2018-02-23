---
title: "Visão geral de segurança e conformidade no Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: "Uma visão geral dos recursos de segurança e conformidade do Microsoft Teams, incluindo auditoria e relatórios, pesquisa de conteúdo de conformidade, eDiscovery e muito mais."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1cb2bfe08736f355f01d55d05be7c7091b79f396
ms.sourcegitcommit: ed40dcf28ae72961fb1f23cf72985cef1d145db0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2018
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Visão geral de segurança e conformidade no Microsoft Teams
======================================================

O Microsoft Teams está criado na nuvem empresarial de grande escala do Office 365, oferecendo os recursos avançados de segurança e conformidade que nossos clientes esperam.

O Teams tem conformidade de Camada C no lançamento. Isso inclui as seguintes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 e SOC 2, HIPAA e EU Model Clauses (EUMC). Dentro da estrutura de conformidade da Microsoft, a Microsoft classifica os aplicativos e serviços do Office 365 em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos por um serviço do Office 365 ou um serviço relacionado da Microsoft para que sejam listados naquela categoria.

Os serviços das categorias de conformidade C e D que têm compromissos de conformidade líderes do setor estão habilitados por padrão. Os serviços das categorias A e B vêm com controles de ativação ou desativação para a organização inteira. Você pode encontrar detalhes em [Estrutura de conformidade para as normas e regulamentos do setor](https://go.microsoft.com/fwlink/?linkid=855777). O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

O Teams também aplica uma autenticação de dois fatores para todas as equipe e organizações, registro único através do diretório ativo e criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote.

Também acrescentamos suporte para pesquisa de registros de auditoria, eDiscovery e retenção legal para canais, bate-papos e arquivos, bem como gerenciamento de aplicativos móveis com o Microsoft Intune.

Essas ferramentas residem no Portal de Segurança e Conformidade do Office 365 e oferecem os seguintes recursos:

-   Auditoria e relatórios

    -   A pesquisa de registros de auditoria se conecta diretamente ao Centro de Segurança e Conformidade do Office 365 e tem a capacidade de configurar alertas e/ou relatórios em um evento de auditoria ao disponibilizar e exportar conjuntos de eventos de carga de trabalho genéricos ou específicos para uso e pesquisa do administrador em uma linha de tempo de auditoria ilimitada. Todos os dados de registro de auditoria estão disponíveis para configurar aletas no Centro de Segurança e Conformidade do Office 365, bem como para filtragem e exportação para análises mais profundas.

-   Pesquisa de conteúdo de conformidade

    -   A pesquisa de conteúdo pode ser usada para fazer pesquisas no Microsoft Teams por meio de funcionalidades sofisticadas de filtragem e exportada para um contêiner específico para dar suporte à conformidade e litígios. Isso pode ser feito com ou sem um caso do eDiscovery.

-   eDiscovery

    -   A descoberta eletrônica é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em uma ação judicial ou investigação.

    -   Os recursos incluem gerenciamento de casos, preservação, pesquisa, análise e exportação dos dados do Teams. Isso inclui bate-papos, mensagens e dados de arquivos.

    -   Os clientes podem se beneficiar do In-place eDiscovery ou do [Advanced eDiscovery](https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)

    -   As diferenças entre os dois estão destacadas na tabela a seguir:


| |In-place eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Gestão de casos     |X        |X         |
|Controle de acesso  |X         |X         |
|Pesquisa de conteúdo     |X         | X        |
|Retenções   |X         | X        |
|Exportar     |X         |X         |
|Detecção de duplicidade     |-         |X         |
|Pesquisa de relevância com aprendizagem de máquina    |-         |X         |
|Análise de dados não estruturados      |-         |X         |


-   Retenção legal

    -   Quando uma equipe do Microsoft Teams é colocada em Bloqueio In-loco ou em Retenção de Litígio, a retenção é colocada na caixa de correio dos grupos.

    -   As retenções locais costumam ser aplicadas no contexto de um caso do eDiscovery.

A figura abaixo indica o fluxo de trabalho dos dados do Teams para o Exchange e o SharePoint.

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> Pode haver um atraso de até 24 horas para revelar o conteúdo do Teams.

Além disso, a Microsoft está considerando oferecer os seguintes recursos de segurança para o Teams. Depois de disponíveis, os clientes serão orientados sobre como fazer uso dos recursos:

-   Política de retenção específico de locatários

-   Prevenção de perda de dados (DLP)

-   Lockbox do cliente

-   Gerenciamento de direitos


| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |Quais são os recursos de segurança e conformidade exigidos pela sua organização? A sua organização tem as licenças necessárias para atender aos requisitos empresariais de segurança e conformidade?         |
|![Ícone de próximos passos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Próximos passos         |Documente os recursos necessários de segurança e conformidade na tabela abaixo.         |

<a name="licensing"></a>Licenças
---------------

Quando falamos em recursos de proteção de informações, as assinaturas do Office 365 e as licenças autônomas associadas determinarão o conjunto de recursos disponíveis.

|Recurso de proteção da informação   |Office 365 Business Essentials   |Office 365 Business Premium   |Office 365 Enterprise E1   |Office 365 Enterprise E3/E4   |Office 365 Enterprise E5   |
|---|---|---|---|---|---|
|Arquivamento|-  |-   |-   |Sim   |Sim   |
|In-Place eDiscovery|-   |-   |-   |Sim   |Sim   |
|Advanced eDiscovery|-   |-   |-   |-   |Sim   |
|Retenção legal|-   |-   |-   |Sim   |Sim   |
|Pesquisa de conteúdo de conformidade|- |- |- |Sim |Sim |
|Auditoria e relatórios|Sim |Sim |Sim |Sim |Sim |
|Acesso condicional* |Sim |Sim |Sim |Sim |Sim |
\*O acesso condicional precisa de licenças adicionais


| |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |A sua organização tem as licenças necessárias para atender aos requisitos empresariais de conformidade e segurança?         |
|![Ícone de próximos passos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Próximos passos         |Revise a licença atual da sua organização e confirme se atende a todos os requisitos empresariais de conformidade e segurança.         |

Antes de habilitar qualquer um desses recursos, certifique-se de ter acesso ao Centro de Segurança e Conformidade do centro de administração do Office 365. Por padrão, os administradores de locatários têm acesso.

A pesquisa de conteúdo e o eDiscovery não precisam de ativação no Centro de Segurança e Conformidade.

<a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams
-------------------------

Os dados no Microsoft Teams residem na região geográfica associada ao seu locatário do Office 365. No momento, o Teams tem suporte na região das Américas, EMEA e APAC. 

> [!IMPORTANT]
> No momento, o Microsoft Teams oferece residência de dados no Reino Unido e na Índia somente para novos locatários. Um novo locatário é definido como aquele que não teve nenhum usuário sequer entrando no Microsoft Teams. Os locatários existentes do Reino Unido e da Índia continuarão nas regiões EMEA e APAC, respectivamente, até que seja anunciado um plano de migração (previsto para 2018).

Para saber mais sobre o lançamento da residência de dados do Microsoft Teams da Índia e do Reino Unido, leia a postagem de Ansuman Acharya no blog, [Microsoft Teams launches India Data Residency, other geos coming soon](https://go.microsoft.com/fwlink/?linkid=867773).

Para ver qual região hospeda os dados de seu locatário, vá para o [Centro de administração do Office 365](https://portal.office.com/adminportal/home) > **Configurações** > **Perfil da organização**. Role para baixo até **Local dos dados**. 

![Captura de tela da tabela Local dos dados, inclusive do Microsoft Teams, no Centro de administração do Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="privacy-in-teams"></a>Privacidade no Microsoft Teams
--------------------------

Como cliente do Office 365, você detém e controla seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso para carregar conteúdo. Assim como o OneDrive for Business e o SharePoint Online, os dados do cliente permanecem no locatário.

Veja mais informações relacionadas a confiabilidade e segurança no [*Centro de Confiabilidade do Office 365*](https://go.microsoft.com/fwlink/?linkid=855779). O Teams segue os mesmos princípios e orientações da Centro de Confiabilidade do Office 365.
