---
title: Dados e Informações de Privacidade
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Dados e Informações de Privacidade
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 5799288005a5d30152a6f810c0aa40d451198390
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270296"
---
# <a name="approach"></a>Abordagem

Os clientes que Salas do Microsoft Teams Serviços Gerenciados confiam à Microsoft seus ativos mais valiosos: os dados. Eles confiam que sua privacidade será protegida e que ela será usada apenas de uma maneira consistente com suas expectativas.

A tecnologia segue os processos de privacidade para garantir que ele cumpra as promessas do cliente em coletar e usar dados efetivamente executando o serviço.
## <a name="data-collection-and-privacy"></a>Privacidade e coleta de dados

 Salas do Microsoft Teams Serviços Gerenciados monitora dispositivos, coleta dados de conteúdo do cliente e acessa e gerencia remotamente os dispositivos como administrador. Os dados coletados são limitados às informações necessárias para monitorar a integridade, a causa raiz e a mitigação de problemas identificados nas salas registradas. Determinados dados coletados são específicos de uma conta de sala, não de usuários individuais.

> [!Note]
> Referências incidentais a um usuário individual podem estar presentes no log de atividades durante o uso do dispositivo.

## <a name="who-can-access-data"></a>Quem pode acessar dados

Os Serviços Gerenciados executam medidas fortes para ajudar a proteger os dados do cliente contra acesso inadequado ou uso por pessoas não autorizadas. Essas medidas incluem restringir o acesso por funcionários e subcontratados da Microsoft.

## <a name="zero-standing-access-data-storage"></a>Armazenamento de dados de Acesso Permanente Zero

Os Serviços Gerenciados atenuam os riscos associados a contas com acesso privilegiado de atores mal-intencionados , dentro e fora de uma organização, por meio do princípio do Acesso Permanente Zero. Esse princípio permite que os Serviços Gerenciados operem sem privilégios disponíveis para qualquer usuário por padrão. Combinado com os princípios do Just-In-Time e do Just-Enough-Access, ele fornece uma estrutura robusta para ser segura e compatível por padrão. Os dados de diagnóstico estão disponíveis para a equipe de operações de serviço da Microsoft por meio de um portal interno.

## <a name="data-handling"></a>Tratamento de dados

A Microsoft é governada por padrões estritos para transmissão, armazenamento, uso e retenção de dados. A Microsoft tem políticas padrão de tratamento de dados que regulam como os dados devem ser tratados com base na classificação de dados.



## <a name="technology-description"></a>Descrição da tecnologia

Os Serviços Gerenciados enviam dados à Microsoft para fins de monitoramento, diagnóstico e mitigação de problemas na implantação. Exemplos incluem

- Garantir que o dispositivo esteja atualizado (incluindo o aplicativo, sistema operacional, drivers, F/W)
- Garantir que o dispositivo esteja pronto para uso (conectado, todos os periféricos que relatam o estado íntegro etc.)
- Garantir que o ambiente esteja pronto (contas provisionadas, velocidades de rede são rápidas o suficiente etc.)
- Determinar se pode haver problemas de hardware ou problemas de instalação (como cabeamento flexível)
- Heurística para determinar problemas (reinicializações excessivas etc.)

Os Serviços Gerenciados gerenciam o dispositivo com as seguintes ações:

- Atualizar software
- Atenuar problemas por meio de reinicializações, redefinindo conexões USB & estados
- Coletar logs específicos para ajudar a diagnosticar problemas

Os Serviços Gerenciados não monitoram nem gravam áudio, vídeo, mídia ou conteúdo de reunião de kits de solução.

### <a name="service-collected-data-categories"></a>Categorias de dados coletadas pelo serviço
 
|Categoria|Detalhes|Motivo da consulta|
| :- | :- | :- |
|Coleta e gerenciamento de dados em andamento|Endereço IP, identidade da conta da sala (Exchange, Skype for Business e/ou Teams), coordenadas de localização, emails e comunicação no portal com a Microsoft ou software|Identificar e conectar-se ao sistema sob gerenciamento; identificar, diagnosticar e atenuar falhas; acompanhar o uso, a análise e os insights; consultar e reparar o status de conectividade|
|Coleta e gerenciamento de dados ad hoc|Informações do log de eventos, atividade do usuário/Identidade do arquivo de log do usuário da sala, juntamente com informações de diagnóstico, consultas de sistema do Windows (exemplos: lista de dispositivos USB, estado de energia etc.)|Identificar, diagnosticar e atenuar falhas e para uso, análise e insights|

Determinados dados confidenciais no log de atividades do dispositivo são editados localmente (não coletados pelos Serviços Gerenciados):

- Assunto e corpo da reunião
- Informações de cartão de visita para os participantes da reunião (como título, número de telefone etc.)
- No conteúdo da mensagem de mensagem de mensagem de mensagem de reunião

> [!NOTE]
> À medida que a Microsoft evolui os Serviços Gerenciados, os dados específicos estão sujeitos a alterações.

### <a name="enrollment"></a>Inscrição

Os Serviços Gerenciados são registrados no portal online para serviços automatizados de monitoramento e suporte, incluindo diagnóstico e relatórios. O registro é feito por meio de comunicações de rede criptografadas usando a chave pública baseada em TPM (Trusted Platform Module) do dispositivo.

### <a name="unenrollment"></a>Cancelar registro

O dispositivo pode ser cancelado ao desinstalar os Serviços Gerenciados. A Microsoft também remove o dispositivo do monitoramento de back-end durante o encerramento e pode excluir os dados coletados na solicitação.
## <a name="compliance"></a>Conformidade

Todos os engenheiros que trabalham no produto precisam passar por treinamento de reconhecimento de segurança e privacidade. A Microsoft também garante que todos os funcionários certifiquem a aceitação das responsabilidades dos requisitos de privacidade.

Os Serviços Gerenciados fornecem suporte à residência de dados regionais por meio dos data centers na Europa (UE), no Pacífico Asiático (APAC) e Estados Unidos (EUA). Os clientes do serviço terão dados relacionados à organização armazenados no data center de sua região escolhida.

## <a name="more-resources"></a>Mais recursos

Salas do Microsoft Teams Segurança:/microsoftteams/rooms/security Microsoft Privacy Statement: https://aka.ms/privacy Gerenciamento de dados na Microsoft: Descrição https://www.microsoft.com/trust-center/privacy/data-management do serviço serviços gerenciados: serviço [gerenciado da Sala do Microsoft Teams](microsoft-teams-rooms-premium.md)
