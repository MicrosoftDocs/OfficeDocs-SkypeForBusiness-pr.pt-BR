---
title: Dados e Informações de Privacidade
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Dados e Informações de Privacidade
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 0aea2402705eb817c7f075cf003245c0ad3258fd
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/11/2022
ms.locfileid: "64757081"
---
# <a name="approach"></a>Abordagem

Os clientes que usam serviços gerenciados confiam à Microsoft seu ativo mais valioso : dados. Eles confiam que sua privacidade será protegida e que ela será usada apenas de uma maneira consistente com suas expectativas.

A tecnologia segue os processos de privacidade para garantir que ele cumpra as promessas do cliente em coletar e usar o serviço de forma eficiente.

## <a name="data-collection"></a>Coleta de dados

Os dados coletados pela Tecnologia são limitados às informações necessárias para monitorar a integridade, a causa raiz e atenuar os problemas identificados nas salas registradas.

A tecnologia monitorará dispositivos, coletará dados de telemetria e permitirá que a Microsoft acesse e gerencie remotamente os dispositivos como administrador.

Os dados de telemetria coletados são específicos de uma conta de sala, não de um usuário individual. Referências incidentais a um usuário individual podem estar presentes no log de atividades durante o uso do dispositivo.

### <a name="who-can-access-your-data"></a>Who pode acessar seus dados

O serviço de tecnologia toma medidas fortes para ajudar a proteger os dados do cliente contra acesso inadequado ou uso por pessoas não autorizadas. Isso inclui restringir o acesso por funcionários e subcontratados da Microsoft.

### <a name="zero-standing-access-data-storage"></a>Dados de acesso permanente zero Armazenamento

A tecnologia reduz os riscos associados a contas com acesso privilegiado – de atores mal-intencionados dentro e fora de uma organização – por meio do princípio do Acesso Permanente Zero. Isso permite que o serviço opere sem privilégios disponíveis para qualquer usuário por padrão. Combinado com os princípios do Just-In-Time e do Just-Enough-Access, ele fornece uma estrutura robusta para ser segura e compatível por padrão. Os dados de diagnóstico estão disponíveis para nossa equipe de operações de serviço por meio de um portal interno.

## <a name="data-handling"></a>Manipulação de dados

A Microsoft é governada por padrões estritos para transmissão, armazenamento, uso e retenção de dados. A Microsoft tem políticas padrão de tratamento de dados que mostram como os dados devem ser tratados com base na classificação de dados.

A Microsoft estende os direitos de proteção de dados do RGPD (Regulamento Geral sobre a Proteção de Dados) para todos os clientes em todo o mundo, não apenas na Europa.

## <a name="data-classification"></a>Classificação de dados

A classificação de dados pode ser usada para aderir aos requisitos e processos de segurança, conformidade e privacidade para coletar, armazenar e usar informações pessoais do usuário.


|Classificação|Descrição|Exemplo|
| :- | :- | :- |
|Conteúdo do Cliente|Conteúdo fornecido/criado diretamente por administradores e usuários.|<p>– BLOB gerado pelo cliente ou dados de armazenamento estruturado</p><p>- Segredos fornecidos/de propriedade do cliente (senhas, certificados, chaves de criptografia, chaves de armazenamento)</p>|
|Informações de identificação do usuário final (EUII)|Dados que identificam ou podem ser usados para identificar o usuário de um serviço da Microsoft. EUII não contém conteúdo do cliente.|<p>- Nome de usuário ou nome de exibição (DOMAIN\UserName)</p><p>- Nome principal do usuário (name@company.com)</p><p>- Endereço IP específico do usuário</p>|
|Dados da Conta|<p>Informações de cobrança do cliente e informações de instrumento de pagamento, incluindo informações de contato do administrador, como locatário</p><p>nome do administrador, endereço ou</p><p>número de telefone.</p>|<p>- Informações de contato do administrador de locatários (por exemplo,</p><p>nome do administrador do locatário, endereço, endereço de email, número de telefone)</p><p>- Provisionamento do cliente</p><p>Informações</p>|
|EUPI (Identificadores Pseudonimosos do Usuário Final)|<p>Um identificador criado pela Microsoft vinculado ao usuário de um serviço da Microsoft. Quando o EUPI é combinado com outras informações, como uma tabela de mapeamento, ele identifica o usuário final. O EUPI não contém informações carregadas ou criadas pelo cliente</p><p>(Conteúdo do cliente ou EUII)</p>|<p>- GUIDs de usuário, PUIDs ou SIDs</p><p>- IDs de sessão</p>|
|Informações de identificação da organização (OII)|Dados que podem ser usados para identificar um locatário, geralmente dados de configuração ou uso. Esses dados não podem ser vinculados a um usuário e não contêm conteúdo do cliente.|<p>- ID do locatário (não GUID)</p><p>- Nome de domínio no endereço de email (xxx@contoso.com) ou outro domínio específico do locatário</p><p>Informações</p>|
|Metadados do sistema|Dados gerados durante a execução do serviço ou programa que não podem ser vinculados a um usuário ou locatário.|<p>- Logs de eventos</p><p>– Dados de uso</p><p>– Dados de configuração</p>|

Descrição da tecnologia

A tecnologia enviará dados à Microsoft para fins de monitoramento, diagnóstico e mitigação de problemas na implantação. Exemplos incluem

1. Garantir que o dispositivo esteja atualizado (incluindo o aplicativo, sistema operacional, drivers, F/W)
1. Garantir que o dispositivo esteja pronto para uso (conectado, todos os periféricos que relatam o estado íntegro etc.)
1. Garantir que o Ambiente esteja pronto (contas provisionadas, velocidades de rede são rápidas o suficiente etc.)
1. Determinar se pode haver problemas de hardware ou problemas de instalação (como cabeamento flexível)
1. Heurística para determinar problemas (reinicializações excessivas etc.) 

A tecnologia gerenciará o dispositivo com ações como

1. Atualizar software
1. Atenuar problemas por meio de reinicializações, redefinindo conexões USB & estados
1. Coletar logs específicos para ajudar a diagnosticar problemas

A tecnologia não monitora nem grava áudio, vídeo, mídia ou conteúdo de reunião dos Kits de Solução. 

### <a name="service-collected-data-categories"></a>Categorias de dados coletadas pelo serviço
 
|Categoria|Detalhes|Motivo da consulta|
| :- | :- | :- |
|Gerenciamento contínuo de & dados|Endereço IP, Identidade da Conta de Sala (Exchange, Skype for Business e/ou Teams), Coordenadas de Localização, Emails e comunicação no Portal com a Microsoft ou software|Identificar e Conexão para o sistema em gerenciamento; Identificar, diagnosticar e atenuar falhas; Acompanhar uso, análise e Insights; Consultar & status de conectividade de reparo|
|Gerenciamento de coleta de dados & ad hoc|<p>Informações do log de eventos, Atividade do Usuário/Identidade do arquivo de log do usuário da Sala, juntamente com informações de diagnóstico, consultas do sistema Windows (exemplos: lista de dispositivos\* USB,</p><p>estado de energia etc.)</p>|Identificar, diagnosticar e atenuar falhas e para uso, análise e Insights|
|<p>Registro de avaliação e</p><p>Instalação</p>|<p>Windows do sistema</p><p>Exemplos: lista de dispositivos USB, estado de energia etc.</p>|<p>Necessário para registro, integração, pedido e entrega,</p><p>e configuração para a Avaliação.</p>|

\* O PII confidencial no log de atividades do dispositivo é redigido localmente (não coletado pela tecnologia):

1. Corpo do Assunto & Reunião
1. Informações de cartão de visita para participantes da reunião (como Título, Telefone Número, etc.)
1. No Conteúdo da Mensagem de Mensagem de Mensagem de Reunião

>> [!NOTE]
>À medida que a Microsoft evolui a tecnologia, os dados específicos estão sujeitos a alterações. 

### <a name="agent-data-classification"></a>Classificação de dados do agente

**Descrição detalhada de todos os dados que o agente MTRP coleta durante o monitoramento contínuo**
|Descrição dos dados coletados|Classificação|
| :- | :- |
|Identidade de um dispositivo compartilhado|OII|
|ID do cliente|OII|
|Local do diretório do Agente MMR|Metadados do sistema|
|Local do diretório de logs do aplicativo MTR|Metadados do sistema|
|Número de Série do Dispositivo|Metadados do sistema|
|Informações de bios do dispositivo|Metadados do sistema|

|Versão do agente MMR|Metadados do sistema|
| :- | :- |
|Versão do aplicativo MTR|Metadados do sistema|
|Versão do aplicativo Teams aplicativo|Metadados do sistema|
|Hora do trabalho de manutenção noturna para o aplicativo MTR|Metadados do sistema|
|URL de atualização do agente MMR|Metadados do sistema|
|Anel do agente MMR|Metadados do sistema|
|Windows do sistema operacional|Metadados do sistema|
|Usuário conectado no momento|Metadados do sistema|
|GUID da sessão do Agente MMR|Metadados do sistema|
|Nome do domínio|Metadados do sistema|
|Tempo desde a última reinicialização do sistema operacional|Metadados do sistema|
|Hora desde o início do último agente MMR|Metadados do sistema|
|Modelo e make do dispositivo MTR|Metadados do sistema|
|Status do dispositivo em uso|Metadados do sistema|
|Tipo de integração de dispositivo|Metadados do sistema|
|Número de monitores conectados|Metadados do sistema|
|Detalhes do locutor MTR|Metadados do sistema|
|Detalhes do microfone MTR|Metadados do sistema|
|Detalhes do alto-falante padrão do MTR|Metadados do sistema|
|Configuração de compartilhamento automático de tela do aplicativo MTR|Metadados do sistema|
|Configuração de anúncio Bluetooth aplicativo MTR|Metadados do sistema|
|Data da última vez em que a senha foi alterada|Metadados do sistema|
|Configuração de rotação de senha MTR|Metadados do sistema|
|Configuração de Teams/Skype for Business MTR|Metadados do sistema|
|Anel de atualização do aplicativo MTR|Metadados do sistema|
|Configuração da câmera de conteúdo do aplicativo MTR|Metadados do sistema|
|Configuração de nomes de reuniões do aplicativo MTR|Metadados do sistema|
|Configuração de exibição do aplicativo MTR na frente da sala|Metadados do sistema|
|GUID do aplicativo MTR|Metadados do sistema|
|Endereço de proxy e porta|Metadados do sistema|
|Integridade do dispositivo MTR|Metadados do sistema|
|Detalhes da conta de sala MTR|OII|
|Endereço IPV4 e endereço IPV6|OII|
|Longitude e latitude|OII|
|Nome do host do dispositivo MTR|OII|
|Fuso horário do dispositivo MTR|Metadados do sistema|
|Status do aplicativo MTR|Metadados do sistema|
|Detalhes do serviço Crestron|Metadados do sistema|
|Versão do firmware da Logitech e versão de sincronização do Logitech|Metadados do sistema|
|Percentual total de CPU em uso|Metadados do sistema|
|RAM total em uso|Metadados do sistema|
|CPU sendo usada por aplicativos MTR Skype ou Teams|Metadados do sistema|
|Temperatura do dispositivo MTR|Metadados do sistema|
|Status das unidades de disco internas|Metadados do sistema|
|Detalhes de falhas de qualquer aplicativo MTR|Metadados do sistema|
|Detalhes de quaisquer vazamentos de memória detectados causados por aplicativos no dispositivo|Metadados do sistema|

|<p>Detalhes de qualquer erro de tela azul do dispositivo que ocorreu sobre o</p><p>últimas 24 horas</p>|Metadados do sistema|
| :- | :- |
|<p>Detalhes de todos os erros que o aplicativo MTR detectou durante as reuniões em</p><p>o dispositivo</p>|Metadados do sistema|
|Detalhes do software instalado|Metadados do sistema|
|Detalhes de hot-fixes instalados/pendentes/ausentes|Metadados do sistema|
|Detalhes de hardware reconhecidos|Metadados do sistema|
|Detalhes de todos os drivers no dispositivo|Metadados do sistema|
|Detalhes de quaisquer correções de dispositivo MMR|Metadados do sistema|
|Detalhes do uso da sala durante as últimas 24 horas, tempo de reuniões e contagens|Metadados do sistema|
|Detalhes das atualizações Windows armazenamento automático|Metadados do sistema|
|Detalhes das Windows do sistema operacional|Metadados do sistema|
|Detalhes de triagem do agente MMR|Metadados do sistema|
|Detalhes do erro de conexão do agente MMR|Metadados do sistema|
|Detalhes sobre se a segurança do TPM está habilitada|Metadados do sistema|
|Detalhes do status de conexão do dispositivo MTR|Metadados do sistema|

**O agente MTRP de dados coleta para diagnóstico e correção de incidentes**
|Descrição dos dados coletados|Classificação|
| :- | :- |
|<p>Logs de eventos: System, Application, Skype Room System, Microsoft- Windows-AppXDeploymentServer%4Operational, Microsoft-Windows- PowerShell%4Operational, Microsoft-Windows- AppXDeployment%4Operational,Microsoft-Windows- AppXDeploymentServer%4Operational, Microsoft-Windows - TWinUI%4Operational, Salas Gerenciadas da Microsoft, Microsoft-Windows-</p><p>TaskScheduler%4Operational, Security</p>|Metadados do sistema|
|Logs de aplicativo MTR editados\*|Metadados do sistema|
|Logs do Microsoft Teams|Metadados do sistema|
|SQLLitedb do agente MMR|Metadados do sistema|
|Detalhes das informações de estado de energia do dispositivo|Metadados do sistema|
|Informações de política de grupo de dispositivos|Metadados do sistema|
|Rastreamento de auditoria de todas as ações do agente MMR|Metadados do sistema|
\* O PII confidencial no log de atividades do dispositivo é redigido localmente.

### <a name="enrollment"></a>Inscrição


Essa tecnologia será registrada no portal online para serviços automatizados de monitoramento e suporte, incluindo diagnóstico e relatórios. O registro é feito por meio de comunicações de rede criptografadas usando a chave pública baseada em TPM (Trusted Platform Module) do dispositivo.

### <a name="un-enrollment"></a>Cancelar registro

O dispositivo pode ser desinstalado desinstalando a tecnologia. A Microsoft também removerá o dispositivo do monitoramento de back-end durante o encerramento e poderá excluir os dados coletados na solicitação.

### <a name="data-flow"></a>Fluxo de dados

A tecnologia adicionará um fluxo de dados do agente aos Serviços Gerenciados de MTR.

![fluxo de dados do agente para os Serviços Gerenciados MTR](../media/data-and-privacy-info-005.png)

Habilitar a integração do Microsoft Defender para Ponto de Extremidade introduzirá um fluxo de dados adicional do Agente MDE para a infraestrutura do Microsoft Defender.

![fluxo de dados adicionais do Agente MDE para o Defender](../media/data-and-privacy-info-006.png)

## <a name="compliance"></a>Conformidade

Todos os engenheiros que trabalham no produto precisam passar por treinamento de reconhecimento de segurança e privacidade. A Microsoft também garante que todos os funcionários certifiquem a aceitação das responsabilidades dos requisitos de privacidade.

A tecnologia fornece suporte regional de residência de dados por meio de datacenters na Europa (UE), Pacífico Asiático (APAC) e Estados Unidos (EUA). Isso significa que os clientes do serviço terão dados relacionados à organização armazenados no datacenter de sua região escolhida.

## <a name="additional-resources"></a>Recursos adicionais

Salas do Microsoft Teams Segurança:/microsoftteams/rooms/security Microsoft Privacy Statement: https://aka.ms/privacy Gerenciamento de dados na Microsoft: a https://www.microsoft.com/trust-center/privacy/data-management descrição do serviço de tecnologia: [Microsoft Teams serviço gerenciado de sala](microsoft-teams-rooms-premium.md)
