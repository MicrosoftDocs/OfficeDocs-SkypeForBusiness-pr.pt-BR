---
title: Visão geral de segurança e conformidade no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
description: Visão geral dos recursos de segurança e conformidade do Microsoft Teams, incluindo auditoria e relatórios, pesquisa de conteúdo de conformidade, eDiscovery e muito mais.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d78f1e0a4f1c3a5ca95dff0f50d688c2d8a6b239
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640782"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Visão geral de segurança e conformidade no Microsoft Teams
======================================================

O Microsoft Teams está criado na nuvem empresarial de grande escala do Office 365, oferecendo os recursos avançados de segurança e conformidade que nossos clientes esperam.

As equipes é compatível com camada D. Isso inclui as seguintes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 e SOC 2, HIPAA e EU Model Clauses (EUMC). Dentro da estrutura de conformidade da Microsoft, a Microsoft classifica os aplicativos e serviços do Office 365 em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos por um serviço do Office 365 ou um serviço relacionado da Microsoft para que sejam listados naquela categoria.

Os serviços das categorias de conformidade C e D que têm compromissos de conformidade líderes do setor estão habilitados por padrão. Os serviços das categorias A e B vêm com controles de ativação ou desativação para a organização inteira. Você pode encontrar detalhes em [Estrutura de conformidade para as normas e regulamentos do setor](https://go.microsoft.com/fwlink/?linkid=855777). O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

O Teams também aplica uma autenticação de dois fatores para todas as equipe e organizações, registro único através do diretório ativo e criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote. Os dados do OneNote são armazenados no site do SharePoint da equipe. Na guia Wiki também pode ser usada para fazer anotações e seu conteúdo também é armazenado no site do SharePoint team.

Também acrescentamos suporte para pesquisa de registros de auditoria, eDiscovery e retenção legal para canais, bate-papos e arquivos, bem como gerenciamento de aplicativos móveis com o Microsoft Intune. Vá para o Centro de conformidade para gerenciar essas configurações de & de segurança do Office 365. 

## <a name="auditing-and-reporting"></a>Auditoria e relatórios

Pesquisa de log de auditoria se conecta à direita para o Centro de conformidade do & de segurança do Office 365 e expõe capacidades para definir alertas e/ou reportar sobre eventos de auditoria, tornando disponível, exportar de carga de trabalho específicos ou evento genérico define para uso de admin e investigação, entre um cronograma de auditoria ilimitada. Todos os dados de Log de auditoria está disponíveis para a configuração de alertas dentro do Centro de conformidade do & de segurança do Office 365, bem como para filtrar e exportar para análise adicional. Consulte este [link](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) para saber mais sobre como realizar uma pesquisa de log de auditoria de eventos do Microsoft Teams no Centro de conformidade do & de segurança do Office 365. 

## <a name="compliance-content-search"></a>Pesquisa de conteúdo de conformidade

Pesquisa de conteúdo pode ser usada para procurar todos os dados de equipes por meio de recursos de filtragem de rich e exportada para um contêiner específico para suporte de conformidade e litígio. Isso pode ser feito com ou sem um caso do eDiscovery. Isso permite que os administradores de conformidade coletar dados de equipes em todos os usuários, revisar e exportá-lo para processamento adicional. Consulte este [link](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) para saber mais sobre como realizar uma pesquisa de conteúdo de conformidade para conteúdo Microsoft Teams o Centro de conformidade do & de segurança do Office 365. 

Dica: Do tipo Microsoft Teams pode ser usado para filtrar por meio Teams Microsoft somente conteúdo, ou seja, Chat e mensagens de canal, reuniões e chamadas. 

## <a name="ediscovery"></a>eDiscovery

A descoberta eletrônica é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em uma ação judicial ou investigação. Recursos incluem o gerenciamento de casos, preservação, pesquisa, análise e exportação de dados de equipes. Isso inclui resumos de bate-papo, mensagens e arquivos, reuniões e chamadas. Para reuniões de equipes e chamadas, um resumo dos eventos que ocorreram na reunião e da chamada são criados e torná-los disponível no eDiscovery. 

Para obter mais detalhes sobre como fazer a descoberta eletrônica no Centro de conformidade de & de segurança e executar a pesquisa de conteúdo de conformidade para conteúdo de equipes, vá para os links abaixo: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Pesquisa de conteúdo](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Os clientes podem aproveitar descoberta eletrônica in-loco ou [eDiscovery Avançado] por seus requisitos (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4). As diferenças entre os dois estão destacadas na tabela a seguir:


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


## <a name="legal-hold"></a>Retenção legal

Durante um litígio, geralmente é necessário que todos os dados associados a um usuário (dos responsáveis) ou uma equipe é preservada imutavelmente, portanto pode ser usada como evidência para o caso. Isso é feito colocando-se um usuário (caixa de correio do usuário) ou uma equipe em retenção legal. Quando qualquer equipe dentro equipes será colocada em (subconjunto do conjunto de sites ou de caixa de correio até o destino de consultas ou conteúdo filtrado) de bloqueio In-loco ou retenção de litígio (coleção inteira de caixa de correio ou site), a retenção é colocada na caixa de correio de grupos. Isso garante que, mesmo se os usuários finais excluir ou editar as mensagens de canal são incluídas na caixa de correio de grupo, imutáveis cópias desse conteúdo são mantidos e estejam disponíveis na pesquisa de descoberta eletrônica. As retenções locais costumam ser aplicadas no contexto de um caso do eDiscovery. Consulte [Este](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) artigo para saber mais sobre preservação e isenções no & de segurança do Office 365 Centro de conformidade da Ajuda. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Arquitetura de proteção de informações para as equipes da Microsoft. 

A figura a seguir indica que o fluxo de inclusão de dados de equipes para Exchange e SharePoint para mensagens e arquivos de equipes. 

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

A figura a seguir indica que o fluxo de inclusão de reuniões de equipes e dados de chamada para o Exchange.

![Diagrama do fluxo de trabalho de reuniões de equipes e dados de chamada para o Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Pode haver até um atraso de 24 horas para descobrir o conteúdo de equipes.

<a name="licensing"></a>Licenças
---------------

Quando falamos em recursos de proteção de informações, as assinaturas do Office 365 e as licenças autônomas associadas determinarão o conjunto de recursos disponíveis.


| Recurso de proteção da informação | Office 365 Business Essentials | Office 365 Business Premium | Office 365 Enterprise E1 | Office 365 Enterprise E3/E4 | Office 365 Enterprise E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              Arquivamento              |               -                |              -              |            -             |             Sim              |           Sim             |
|        In-Place eDiscovery        |               -                |              -              |            -             |             Sim              |           Sim             |
|        Advanced eDiscovery        |               -                |              -              |            -             |              -              |           Sim            |
|            Retenção legal             |               -                |              -              |            -             |             Sim              |           Sim             |
|     Pesquisa de conteúdo de conformidade     |               -                |             Sim              |           Sim             |             Sim              |           Sim             |
|      Auditoria e relatórios       |              Sim               |             Sim              |           Sim             |             Sim              |           Sim             |
|       Acesso condicional\*        |              Sim                |             Sim              |           Sim             |             Sim              |           Sim            |

> [!NOTE]
> \*O acesso condicional precisa de licenças adicionais


| |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |A sua organização tem as licenças necessárias para atender aos requisitos empresariais de conformidade e segurança?         |
|![Ícone de próximos passos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Próximos passos         |Revise o licenciamento atual da sua organização e confirme que ele atenda todos os requisitos de negócios para conformidade e segurança.         |

Antes de habilitar qualquer um desses recursos, verifique se que você tem acesso para o Centro de conformidade do & de segurança no Centro de administração do Office 365. Por padrão, os administradores de locatários têm acesso.

Pesquisa de conteúdo e descoberta eletrônica não exigem habilitação do Centro de conformidade do & de segurança.

<a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams
-------------------------

Os dados no Microsoft Teams residem na região geográfica associada ao seu locatário do Office 365. Atualmente, equipes suporta as regiões da Austrália, Canadá, Índia, Japão, Reino Unido, Américas, APAC e EMEA. 

> [!IMPORTANT]
> As equipes atualmente oferece residência de dados na Austrália, Canadá, Índia, Japão e Reino Unido para os novos locatários apenas. Um novo locatário é definido como aquele que não teve nenhum usuário sequer entrando no Microsoft Teams. Inquilinos existentes da Austrália, Índia e Japão continuarão a suas equipes dos dados armazenadas na região APAC. Inquilinos existentes no Canadá e Reino Unido terão seus dados armazenados nas Américas e região EMEA, respectivamente.

Para saber mais sobre o lançamento da residência de dados do Microsoft Teams da Índia e do Reino Unido, leia a postagem de Ansuman Acharya no blog, [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827). 

Para obter mais informações em residência de dados do Canadá para equipes, leia a postagem do blog de Varun Sagar, [residência de dados do Microsoft equipes inicia no Canadá, Austrália e Japão em breve](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Para saber mais sobre o lançamento do Austrália e Japão residência de dados para equipes, leia a postagem do blog de Varun Sagar, [Microsoft equipes inicia Austrália e Japão dados residência ](https://go.microsoft.com/fwlink/?linkid=867773). 

Para ver qual região armazena dados para seu locatário, vá para o [Centro de administração do Office 365](https://portal.office.com/adminportal/home) > **configurações** > **perfil da organização**. Role para baixo até **Local dos dados**. 

![Captura de tela da tabela de dados local, incluindo as equipes, no Centro de administração do Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Como funcionam as políticas de acesso condicional para equipes?
-------------------------

Microsoft Teams depende muito Exchange Online, SharePoint Online e Skype para Business Online para cenários de produtividade de núcleo, como reuniões, calendários, interoperabilidade de bate-papos e compartilhamento de arquivos. Políticas de acesso condicional que são definidas para esses aplicativos de nuvem se aplicam ao Microsoft Teams quando um usuário diretamente entra no Microsoft Teams - em qualquer cliente. 

Microsoft Teams é suportada separadamente como um aplicativo de nuvem em políticas de acesso condicional do Azure Active Directory. Políticas de acesso condicional que são definidas para o aplicativo de nuvem da Microsoft Teams se aplicam ao Microsoft Teams quando um usuário entrar. No entanto, sem as políticas corretas em outros aplicativos como o Exchange Online e SharePoint Online, os usuários ainda poderá acessar esses recursos diretamente. Para obter mais informações sobre como configurar uma política de acesso condicional no portal do azure, vá para: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Clientes de desktop Teams da Microsoft para Windows e Mac suportam a autenticação moderna. Autenticação moderna traz entrar com base no Azure Active Directory autenticação biblioteca (ADAL) para aplicativos cliente do Microsoft Office em todas as plataformas.

Aplicativo de área de trabalho do Microsoft Teams suporta AppLocker.  Para obter mais informações sobre os pré-requisitos do AppLocker, consulte: requisitos para usar o AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

<a name="privacy-in-teams"></a>Privacidade no Microsoft Teams
--------------------------

Como cliente do Office 365, você detém e controla seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso para carregar conteúdo. Assim como o OneDrive for Business e o SharePoint Online, os dados do cliente permanecem no locatário.

Confira mais sobre nossos confiabilidade e segurança relacionados informações no [Microsoft Central de confiabilidade](https://microsoft.com/trustcenter). As equipes segue as diretrizes e os princípios a mesma como a Microsoft Trust Center.
