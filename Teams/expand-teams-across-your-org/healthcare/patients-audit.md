---
title: 'Aplicativo Pacientes de Auditoria para EQUIPES DE EQUIPES e administradores de conformidade '
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
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: Saiba como auditar o aplicativo Pacientes para administradores do Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ce1851b6d424203f6a4aed8a871209e3a65ce5f8
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803509"
---
# <a name="audit-logs-for-patients-app"></a>Logs de auditoria para o aplicativo de pacientes

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio de grupo do grupo do Office 365 que faz o back-back da equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas de novo usando o [aplicativo Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Com listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de meleções até o monitoramento geral dos pacientes. Confira o modelo Pacientes em Listas para começar. Para saber mais sobre como gerenciar o aplicativo Listas em sua organização, consulte [Gerenciar o aplicativo Listas.](../../manage-lists-app.md)

Um log de auditoria da atividade do aplicativo Pacientes permite que as equipes de resposta após incidentes revisem as alterações nos Registros Médicos Eletrônicos (EMR) ou Informações de Saúde do Paciente (PHI) de um paciente e determinam se são necessárias alterações ou melhorias na política ou no procedimento para o acesso phi em ferramentas de produtividade. Os eventos de log de auditoria abrangem as ações executadas por meio da interface do usuário do aplicativo Pacientes.

## <a name="meet-hipaa-requirements"></a>Atender aos requisitos da HIPAA

De acordo com as diretrizes da HIPAA, os provedores de saúde são obrigados a manter registros de todo o acesso ao PHI, para que seja possível que as alterações sejam auditadas. A Microsoft tem o compromisso de seus clientes corporativos usando o Microsoft Teams e de ajudá-los a atender aos requisitos e controles HIPAA. O acesso ao PHI por meio do aplicativo Pacientes é totalmente rastreado e os logs são disponibilizados no Centro de Conformidade do Microsoft 365, conforme descrito no artigo de funcionalidade pesquisa de [log de](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) auditoria.

> [!IMPORTANT]
> A responsabilidade de manter a privacidade do paciente é colocada no provedor de serviços de saúde por lei. A lei dá direito aos pacientes à privacidade e exige que um administrador de IT ou controlador HIPAA possa determinar facilmente qual enfermeira, médica ou assistente social acessou ou alterou registros de pacientes. Um dos exemplos mais comuns de uma violação de acesso PHI é o acesso a pacientes VIP. A funcionalidade do log de auditoria é necessária para conduzir investigações de qualquer violação de acesso PHI e para atender aos requisitos da HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Habilitar logs de auditoria para o aplicativo Pacientes

Uma Auditoria depende de várias configurações anteriores:

1. O administrador teria que trabalhar com o provedor de serviços FHIR para ter a EMR em um formato usado pelo aplicativo Pacientes. Consulte [Integração de registros de assistência médica eletrônica ao Microsoft Teams.](patients-app.md)
2. Um administrador de provedor de serviços de saúde teria que habilitar o aplicativo pacientes no Centro de administração do Teams. Consulte [Gerenciar políticas de configuração de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md) e artigos relacionados para obter mais informações.
3. O administrador teria que habilitar auditorias de atividades, da mesma [](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) forma que ele habilita qualquer auditoria de log de atividades, conforme descrito em Antes de começar e ativar ou desativar a pesquisa de log de [auditoria.](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) Se o log de auditoria já estiver on, nada de especial será necessário para o aplicativo Pacientes. Sempre que um provedor de serviços de saúde instala e executa o aplicativo em uma Equipe, os logs de auditoria registram sua atividade phi.
4. O administrador precisaria então anunciar a disponibilidade do aplicativo Pacientes, e os profissionais de saúde teriam que começar a gerar atividades para serem incluídos em uma auditoria.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Executar uma auditoria

Para obter instruções sobre como executar uma pesquisa do log de atividades, consulte [Pesquisar o log de auditoria.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>Atividades registradas para o aplicativo Pacientes

O aplicativo Pacientes tem suas próprias atividades registradas, listadas na tabela a seguir:

|Nome amigável |Operação|Descrição|
|:---|:---|:---|
| Lista de pacientes exibida | PatientListView | Um usuário exibiu uma lista de pacientes.|
| Lista de pacientes excluídos | PatientListDelete | Um usuário excluiu uma lista de pacientes.|
| Paciente adicionado à lista | PatientListAddPatient | Um paciente foi adicionado a uma lista de pacientes. |
| Anotação adicionada para paciente | PatientNoteAdd | Uma anotação foi adicionada a um registro de paciente. |
| Esquema de pacientes criado | PatientSchemaCreate | Um conjunto de colunas usadas no registro do paciente foi criado. |
| O usuário iniciou uma exportação | ExportInitiation | Os dados dos pacientes foram exportados do aplicativo Pacientes para um arquivo do Excel. O arquivo será salvo no site do SharePoint da equipe. |
| Lista de pacientes criada | PatientListCreate | Um usuário criou uma lista de pacientes.|
| Definir lista de pacientes padrão| PatientListDefaultSet| Um usuário definir uma lista específica como a lista padrão.|
| Paciente removido da lista| PatientListRemovePatient | Um paciente foi removido de uma lista de pacientes. |
| Paciente pesquisado | Pesquisado Paciente | Pesquisou um registro de paciente no serviço EHR. |
| Esquema de pacientes atualizado | PatientSchemaUpdate  | Atualizado um conjunto de colunas existente usado no registro do paciente. |<!-- | Paciente movido para uma lista diferente| PatientMoved | O registro do paciente foi movido de uma lista para outra. |-->
| Lista de pacientes renomeada | NomedoArm paciente | Uma lista de pacientes foi renomeada. |
| Colunas editadas na lista de pacientes | PatientListEditColumns | Uma coluna em uma lista de pacientes foi editada (adicionada ou removida). |
| Detalhes do paciente exibidos | PatientView | Um usuário exibiu um registro de paciente.|
| Detalhes do paciente editado | PatientDetailsEdit | Um detalhe sobre um registro de paciente foi editado. |
| Definir conexão EHR | EHRConnectionSet | De definir a URL usada para se conectar à conexão do Serviço EHR FHIR. Exemplo: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

Você pode personalizar sua Auditoria conforme necessário para pesquisar ou filtrar qualquer uma dessas atividades registradas.

As atividades registradas do Microsoft Teams em geral são descritas nas [atividades do Microsoft Teams.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>Tópicos relacionados

[Pesquisar o log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integração dos Registros Eletrônicos de Saúde no Microsoft Teams](patients-app.md)
