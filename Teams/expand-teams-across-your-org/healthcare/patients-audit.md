---
title: 'Auditando o aplicativo Pacientes para Teams de CONFORMIDADE e conformidade '
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
description: Saiba mais sobre como auditar o aplicativo Patients para Teams administradores
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a2c5b006384d113dde82f702dee68a82b99685f6
ms.sourcegitcommit: e6e6a2a85ff376f97a3af3548e13d1273fa84a52
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697828"
---
# <a name="audit-logs-for-patients-app"></a>Logs de auditoria para o aplicativo de pacientes

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes será retirado e substituído pelo [aplicativo de Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio do grupo do Office 365 que apoia a equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas usando o [aplicativo Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Com o Lists, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam desde reuniões gerais com a equipe de atendimento até o monitoramento geral dos pacientes. Confira o modelo Pacientes no Lists para começar. Para saber mais sobre como gerenciar o aplicativo Lists em sua organização, consulte [Gerenciar o aplicativo Lists](../../manage-lists-app.md).

Um log de auditoria para atividades de aplicativos de pacientes permite que as equipes de resposta após incidentes revisem as alterações nos Registros Médicos Eletrônicos (EMR) de um paciente ou no PHI (Patient Healthcare Information) e determinam se alterações ou melhorias na política ou no procedimento para o acesso à PHI nas ferramentas de produtividade são necessárias. Os eventos de log de auditoria abrangem ações realizadas por meio da interface de usuário do aplicativo Patients.

## <a name="meet-hipaa-requirements"></a>Atender aos requisitos HIPAA

De acordo com as diretrizes hipaaa, os provedores de saúde são necessários para manter registros de todo o acesso à PHI, para que seja possível que as alterações sejam auditadas. A Microsoft está comprometida com seus clientes corporativos usando Microsoft Teams e para ajudá-los a atender aos requisitos e controles HIPAA. O acesso ao PHI por meio do Aplicativo de Pacientes é totalmente rastreado e os logs são disponibilizados no centro de Conformidade Microsoft 365, conforme descrito no artigo de funcionalidade de Pesquisa de [Log de](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) Auditoria.

> [!IMPORTANT]
> A responsabilidade de manter a privacidade do paciente é colocada no provedor de saúde por lei. A lei dá aos pacientes acesso à privacidade e exige que um administrador de IT ou controlador HIPAA possa determinar facilmente quais registros de pacientes foram acessados ou alterados por um profissional de saúde. Um dos exemplos mais comuns de uma violação de acesso à PHI é o acesso a pacientes VIP. A funcionalidade de log de auditoria é necessária para conduzir investigações de qualquer violação de acesso à PHI e atender aos requisitos hipaaa.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Habilitar logs de auditoria para o Aplicativo de Pacientes

Uma Auditoria depende de várias configurações anteriores:

1. O administrador teria que trabalhar com o provedor de serviços FHIR para ter a EMR em um formato usado pelo Aplicativo de Pacientes. 
2. Um administrador do provedor de saúde teria que habilitar o aplicativo de pacientes Teams Centro de Administração. Consulte [Gerenciar políticas de configuração de aplicativos em Microsoft Teams](../../teams-app-setup-policies.md) e artigos relacionados para obter mais informações.
3. O administrador teria que habilitar auditorias de atividade, da mesma forma que habilitam qualquer auditoria de log de [atividades,](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)conforme descrito em Before you [begin](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) and Turn audit log search on or off . Se o log de auditoria já estiver on, nada de especial será necessário para o Aplicativo de Pacientes. Sempre que um provedor de saúde instala e executa o aplicativo em uma Equipe, os logs de auditoria registram suas atividades phi.
4. O administrador precisaria então anunciar a disponibilidade do aplicativo Pacientes, e os funcionários de Saúde teriam que começar a gerar atividades para serem incluídos em uma auditoria.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Executar uma auditoria

Para obter instruções sobre como executar uma pesquisa do log de atividades, consulte [Pesquisar o log de auditoria](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

## <a name="logged-activities-for-patients-app"></a>Atividades registradas para o aplicativo Pacientes

O aplicativo Patients tem suas próprias atividades registradas, listadas na tabela a seguir:

|Nome amigável | Operação | Descrição|
|:---|:---|:---|
| Lista de pacientes exibida | PatientListView | Um usuário exibiu uma lista de pacientes.|
| Lista de pacientes excluídos | PatientListDelete | Um usuário excluiu uma lista de pacientes.|
| Adicionado paciente à lista | PatientListAddPatient | Um paciente foi adicionado a uma lista de pacientes. |
| Observação adicionada para o paciente | PatientNoteAdd | Uma observação foi adicionada a um registro de paciente. |
| Esquema de paciente criado | PatientSchemaCreate | Um conjunto de colunas usadas no registro do paciente foi criado. |
| O usuário iniciou uma exportação | ExportInitiation | Os dados do paciente foram exportados do aplicativo Patients para um arquivo Excel de pacientes. O arquivo será salvo no site do SharePoint team. |
| Lista de pacientes criada | PatientListCreate | Um usuário criou uma lista de pacientes.|
| Definir lista de pacientes padrão| PatientListDefaultSet| Um usuário definir uma lista específica como a lista padrão.|
| Paciente removido da lista| PatientListRemovePatient | Um paciente foi removido de uma lista de pacientes. |
| Paciente pesquisado | PatientSearch | Pesquisou um registro de paciente no serviço EHR. |
| Esquema de paciente atualizado | PatientSchemaUpdate  | Atualizado um conjunto existente de colunas usadas no registro do paciente. |<!-- | Movido paciente para uma lista diferente| PatientMoved | O registro do paciente foi movido de uma lista para outra. |-->
| Lista de pacientes renomeadas | PatientListRename | Uma lista de pacientes foi renomeada. |
| Colunas editadas na lista de pacientes | PatientListEditColumns | Uma coluna em uma lista de pacientes foi editada (adicionada ou removida). |
| Detalhes do paciente exibidos | PatientView | Um usuário exibiu um registro de paciente.|
| Detalhes do paciente editado | PatientDetailsEdit | Um detalhe em um registro de paciente foi editado. |
| Definir conexão EHR | EHRConnectionSet | De definir a URL usada para se conectar à conexão de Serviço EHR FHIR. Exemplo: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |

Você pode personalizar sua Auditoria conforme necessário para pesquisar ou filtrar qualquer uma dessas atividades registradas.

As atividades registradas para Microsoft Teams em geral são descritas [em Microsoft Teams atividades](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities).

## <a name="related-topics"></a>Tópicos relacionados

[Pesquisar o log de auditoria](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
