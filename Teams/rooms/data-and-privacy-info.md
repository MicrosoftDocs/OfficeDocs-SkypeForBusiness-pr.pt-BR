---
title: Informações de privacidade e dados
author: altsou
ms.author: altsou
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
description: Informações de privacidade e dados
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: dd80718da862be02b42a5cf18334c89e86c3807c
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438427"
---
# <a name="approach"></a>Abordagem

Os clientes que usam Salas do Microsoft Teams Serviços Gerenciados confiam Microsoft com seus dados de ativos mais valiosos. Eles confiam que sua privacidade será protegida e que ela será usada apenas de uma maneira consistente com suas expectativas.

A tecnologia segue processos de privacidade para garantir que ela siga as promessas do cliente na coleta e no uso de dados que executam efetivamente o serviço.
## <a name="data-collection-and-privacy"></a>Coleta de dados e privacidade

 Salas do Microsoft Teams Serviços Gerenciados monitora dispositivos, coleta dados de conteúdo do cliente e acessa remotamente e gerencia os dispositivos como administrador. Os dados coletados são limitados às informações necessárias para monitorar a integridade, a causa raiz e os problemas de mitigação identificados nas salas registradas. Determinados dados coletados são específicos para uma conta de sala, não para usuários individuais.

> [!Note]
> Referências incidentais a um usuário individual podem estar presentes no log de atividades durante o uso do dispositivo.

## <a name="who-can-access-data"></a>Quem pode acessar dados

Os Serviços Gerenciados adotam medidas fortes para ajudar a proteger os dados do cliente contra acesso ou uso inadequado por pessoas não autorizadas. Essas medidas incluem restringir o acesso por Microsoft funcionários e subcontratados.

## <a name="zero-standing-access-data-storage"></a>Armazenamento de dados do Acesso Permanente Zero

Os Serviços Gerenciados mitigam os riscos associados a contas com acesso privilegiado de atores mal-intencionados, dentro e fora de uma organização, por meio do princípio do Acesso Permanente Zero. Esse princípio permite que os Serviços Gerenciados operem sem privilégios disponíveis para qualquer usuário por padrão. Combinado com os princípios de Just-In-Time e Just-Enough-Access, ele fornece uma estrutura robusta para ser segura e compatível por padrão. Os dados de diagnóstico estão disponíveis para a equipe de operações de serviço Microsoft por meio de um portal interno.

## <a name="data-handling"></a>Tratamento de dados

Microsoft é regido por padrões rígidos para transmissão, armazenamento, uso e retenção de dados. Microsoft tem políticas padrão de tratamento de dados que regulam como os dados devem ser tratados com base na classificação de dados.

## <a name="technology-description"></a>Descrição da tecnologia

Os Serviços Gerenciados enviam dados para Microsoft para fins de monitoramento, diagnóstico e mitigação de quaisquer problemas na implantação. Exemplos incluem

- Garantir que o dispositivo esteja atualizado (incluindo o aplicativo, o sistema operacional, os drivers, o F/W)
- Garantir que o dispositivo esteja pronto para usar (conectado, todos os periféricos relatando estado saudável etc.)
- Garantir que o ambiente esteja pronto (contas provisionadas, velocidades de rede são rápidas o suficiente, etc.)
- Determinar se pode haver problemas de hardware ou problemas de instalação (como cabeamento solto)
- Heurística para determinar problemas (reinicializações excessivas etc.)

Os Serviços Gerenciados gerenciam o dispositivo com as seguintes ações:

- Atualizar software
- Atenuar problemas por meio de reinicializações, redefinindo conexões USB & estados
- Coletar logs específicos para ajudar a diagnosticar problemas

Os Serviços Gerenciados não monitoram ou gravam conteúdo de áudio, vídeo, mídia ou reunião de kits de solução.

### <a name="service-collected-data-categories"></a>Categorias de dados coletadas pelo serviço
 
|Categoria|Detalhes|Motivo para consulta|
| :- | :- | :- |
|Coleta e gerenciamento de dados em andamento|Endereço IP, identidade da conta da sala (Exchange, Skype for Business e/ou Teams), coordenadas de localização, emails e comunicação no portal com Microsoft ou software|Identificar e conectar-se ao sistema sob gerenciamento; identificar, diagnosticar e mitigar falhas; controlar o uso, a análise e os insights; status de conectividade de consulta e reparo|
|Coleta e gerenciamento de dados ad hoc|Informações de log de eventos, atividade do usuário/Identidade do usuário da sala registradas no arquivo de log junto com informações de diagnóstico, consultas do sistema Windows (Exemplos: Lista de dispositivos USB, estado de energia etc.)|Identificar, diagnosticar e mitigar falhas e para uso, análise e insights|

Determinados dados confidenciais no log de Atividade do Dispositivo são redigidos localmente (não coletados pelos Serviços Gerenciados):

- Assunto e corpo da reunião
- Informações de cartão de contato para participantes da reunião (como título, número de telefone etc.)
- No conteúdo da mensagem IM da reunião

> [!NOTE]
> À medida que Microsoft evolui os Serviços Gerenciados, os dados específicos estão sujeitos a alterações.

### <a name="enrollment"></a>Inscrição

Os Serviços Gerenciados são registrados no portal online para serviços automatizados de monitoramento e suporte, incluindo diagnóstico e relatórios. O registro é feito por meio de comunicações de rede criptografadas usando a chave pública baseada no TPM (Módulo de Plataforma Confiável) do dispositivo.

### <a name="unenrollment"></a>Unenrollment

O dispositivo pode ser desinstalado desinstalando serviços gerenciados. Microsoft também remove o dispositivo do monitoramento de back-end durante o descomissionamento e pode excluir dados coletados sob solicitação.
## <a name="compliance"></a>Conformidade

Todos os engenheiros que trabalham no produto são obrigados a passar por treinamento de conscientização sobre segurança e privacidade. Microsoft também garante que todos os funcionários certifiquem a aceitação das responsabilidades pelos requisitos de privacidade.

Os Serviços Gerenciados fornecem suporte à residência de dados regional por meio dos data centers na Europa (UE), Ásia-Pacífico (APAC) e Estados Unidos (EUA). Os clientes de serviço terão dados relacionados à organização armazenados no data center da região escolhida.

## <a name="more-resources"></a>Mais recursos

Salas do Microsoft Teams na segurança do Windows: [[Microsoft Teams para segurança do Windows](/microsoftteams/rooms/security-windows) \
Salas do Microsoft Teams na segurança do Android: [segurança do Microsoft Teams para Android](/microsoftteams/rooms/security-android) \
Microsoft Instrução de Privacidade:https://aka.ms/privacy \
Gerenciamento de dados no Microsoft:https://www.microsoft.com/trust-center/privacy/data-management \
Descrição do serviço dos Serviços Gerenciados: [Microsoft serviço gerenciado do Teams Room](rooms-pro-management.md)
