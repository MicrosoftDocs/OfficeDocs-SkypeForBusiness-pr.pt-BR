---
title: 'Aplicativo de auditoria de pacientes para administradores de ti e conformidade do teams '
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
description: Aplicativo pacientes para administradores do teams
ms.openlocfilehash: 2b61f7a923d863086b09d240230a0eb8e5ca897b
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277235"
---
# <a name="audit-logs-for-patients-app"></a>Logs de auditoria para o aplicativo de pacientes

> [!IMPORTANT]
> **A partir de 30 de setembro de 2020, o aplicativo pacientes será preterido, e os usuários não poderão mais instalá-lo na App Store da equipe. Recomendamos que você comece a usar o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Microsoft Teams hoje mesmo.**
>
>Os dados do aplicativo pacientes são armazenados na caixa de correio do grupo do grupo do Office 365 que faz a equipe. Quando o aplicativo pacientes é desativado, todos os dados associados a ele serão mantidos nesse grupo, mas não poderão mais ser acessados por meio da interface do usuário. Os usuários atuais podem recriar suas listas usando o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>O [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal. Com listas, o cuidado com equipes pode criar listas de pacientes usando o modelo de pacientes incorporado, do zero ou importando dados para o Excel. Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).

Um log de auditoria para atividades de aplicativo pacientes permite que as equipes de resposta a incidentes revisem alterações para os registros médicos eletrônicos (EMR) ou informações de assistência médica (PHI) de um paciente e determine se alterações ou melhorias na política ou nos procedimentos para o acesso PHI em ferramentas de produtividade são necessárias. Os eventos de log de auditoria abordam as ações realizadas por meio da interface de usuário do aplicativo pacientes.

## <a name="meet-hipaa-requirements"></a>Conheça os requisitos da HIPAA

De acordo com as diretrizes da HIPAA, os provedores de assistência médica são necessários para manter registros de todo o acesso a PHI, para que seja possível que as alterações sejam auditadas. A Microsoft está comprometida com seus clientes empresariais que usam o Microsoft Teams e para ajudá-los a atender aos requisitos e controles da HIPAA. O acesso a PHI pelo aplicativo pacientes é totalmente controlado e os logs são disponibilizados no centro de conformidade do Microsoft 365, conforme descrito no artigo [funcionalidade de pesquisa de log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) .

> [!IMPORTANT]
> A responsabilidade de manter a privacidade do paciente é colocada no provedor de assistência médica por lei. A lei concede aos pacientes a privacidade e requer que um administrador de ti ou um controlador de HIPAA possa determinar facilmente qual enfermeira, clínico ou trabalhador social acessou ou alterou registros de pacientes. Um dos exemplos mais comuns de uma violação de acesso PHI é o acesso a pacientes VIP. A funcionalidade do log de auditoria é necessária para conduzir investigações de qualquer violação de acesso Fi e para atender às exigências da HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Habilitar logs de auditoria para o aplicativo pacientes

Uma auditoria depende de várias configurações anteriores:

1. O administrador teria que trabalhar com o provedor de serviços FHIR para ter o EMR em um formato usado pelo aplicativo pacientes. Confira [integrando os registros eletrônicos de assistência médica ao Microsoft Teams](patients-app.md).
2. Um administrador de provedor de assistência médica precisaria habilitar o aplicativo pacientes no centro de administração do teams. Consulte [gerenciar políticas de configuração de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md) e artigos relacionados para obter mais informações.
3. O administrador teria que habilitar as auditorias de atividades, da mesma forma que habilitam qualquer auditoria de log de atividades, conforme descrito em [antes de você começar](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) e [Ativar ou desativar a pesquisa de log de auditoria](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search). Se o log de auditoria já estiver ativado, nada de especial será necessário para o aplicativo pacientes. Sempre que um provedor de assistência médica instalar e executar o aplicativo dentro de uma equipe, os logs de auditoria registrarão suas atividades de PHI.
4. Em seguida, o administrador precisaria anunciar a disponibilidade do aplicativo pacientes, e os funcionários da área de saúde precisariam começar a gerar atividades a serem incluídas em uma auditoria.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Executar uma auditoria

Para obter instruções sobre como executar uma pesquisa no log de atividades, consulte [Pesquisar no log de auditoria](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

## <a name="logged-activities-for-patients-app"></a>Atividades registradas para o aplicativo pacientes

O aplicativo pacientes tem suas próprias atividades registradas, listadas na tabela a seguir:

|Nome amigável |Operação|Descrição|
|:---|:---|:---|
| Lista de pacientes exibida | PatientListView | Um usuário exibiu uma lista de pacientes.|
| Lista de pacientes excluídos | PatientListDelete | Um usuário excluiu uma lista de pacientes.|
| Adicionar paciente à lista | PatientListAddPatient | Um paciente foi adicionado a uma lista de pacientes. |
| Foi adicionada uma nota para pacientes | PatientNoteAdd | Uma anotação foi adicionada a um registro de paciente. |
| Esquema de paciente criado | PatientSchemaCreate | Um conjunto de colunas usado no registro de paciente foi criado. |
| O usuário iniciou uma exportação | ExportInitiation | Os dados dos pacientes foram exportados do aplicativo pacientes para um arquivo do Excel. O arquivo será salvo no site do SharePoint da equipe. |
| Lista de pacientes criada | PatientListCreate | Um usuário criou uma lista de pacientes.|
| Definir lista de pacientes padrão| PatientListDefaultSet| Um usuário define uma lista específica como a lista padrão.|
| Removida a lista de pacientes| PatientListRemovePatient | Um paciente foi removido de uma lista de pacientes. |
| Pesquisar paciente | PatientSearch | Pesquisado um registro de paciente no serviço EHR. |
| Esquema do paciente atualizado | PatientSchemaUpdate  | Atualização de um conjunto existente de colunas usado no registro de pacientes. |<!-- | Movimento do paciente para uma lista diferente| PatientMoved | O registro de paciente foi movido de uma lista para outra. |-->
| Lista de pacientes renomeadas | PatientListRename | Uma lista de pacientes foi renomeada. |
| Colunas editadas na lista de pacientes | PatientListEditColumns | Uma coluna em uma lista de pacientes foi editada (adicionada ou removida). |
| Detalhes do paciente exibido | PatientView | Um usuário exibiu um registro de paciente.|
| Detalhes do paciente editado | PatientDetailsEdit | Um detalhe sobre um registro de paciente foi editado. |
| Definir conexão EHR | EHRConnectionSet | Defina a URL usada para se conectar à conexão do serviço EHR FHIR. Exemplo: https://<span>API-V8-dstu2.hspconsortium.org/ContosoHospital/Open</span>  |
||||

Você pode personalizar sua auditoria conforme necessário para pesquisar ou filtrar em qualquer uma dessas atividades registradas.

As atividades registradas para o Microsoft Teams em geral estão descritas em [atividades do Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities).

## <a name="related-topics"></a>Tópicos relacionados

[Pesquisar no log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integração dos Registros Eletrônicos de Saúde no Microsoft Teams](patients-app.md)
