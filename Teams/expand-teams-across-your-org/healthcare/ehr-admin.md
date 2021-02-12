---
title: Equipes para visitas virtuais
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usar o Microsoft Teams para configurar seu sistema de visitas virtuais
ms.openlocfilehash: 2d2be135668bcc45f0054e987a23845e3245c38e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125774"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Visitas virtuais com o Teams – Integração com o EHR

O Microsoft Teams Electronic Health Record (EHR) Connector facilita a entrada de pacientes virtuais ou consulta com outro provedor no Teams diretamente do sistema EHR. Criado na nuvem do Microsoft 365, o Microsoft Teams permite colaboração e comunicação simples e seguras com ferramentas de chat, vídeo, voz e saúde em um único hub que oferece suporte à conformidade com a HIPAA, certificação HITECH e muito mais.
A plataforma de comunicação e colaboração do Teams facilita a recortar a confusão de sistemas fragmentados para que eles possam passar o tempo fornecendo o melhor cuidado possível. O Microsoft Teams Electronic Health Record (EHR) Connector pode:
- Iniciar visitas virtuais do Teams a partir de portais de provedores e pacientes.
- Escreva novamente nos metadados EHR ao conectar e desconectar eventos para habilitar a auditoria automática e a manutenção de registros.
- Integre-se aos fluxos de trabalho dos pacientes e dos fluxos de trabalho existentes, permitindo que eles usem o Microsoft Teams.

  Assista ao vídeo sobre como gerenciar visitas virtuais no portal do EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>Antes de você começar

Você precisará garantir que tem os seguintes pré-requisitos antes de integrar o conector EHR:

- Acesso para usar o aplicativo Microsoft Teams no [Marketplace do App Pomar do App.](https://apporchard.epic.com/Gallery?id=6153)

- Assinatura ativa do Microsoft Cloud for Healthcare ou assinatura da oferta autônoma do Microsoft Teams EHR Connector (imposta somente durante os testes de produção).

- Os usuários devem ter uma licença apropriada do Microsoft 365 ou do Office 365 que inclua reuniões do Microsoft Teams.

- O Microsoft Teams deve ser adotado e usado dentro da organização.

- As organizações devem ter a versão Original de novembro de 2018 ou posterior.

- Seus sistemas devem atender a [todos os pré-requisitos](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)de software e navegador.

Você também precisará de informações das seguintes pessoas em sua organização:

- Administrador do Microsoft 365

- Analista de clientes com experiência em negócios

> [!Note]
> Solicite ao seu especialista técnico da Base de Dados para fornecer o Epic-Microsoft de Integração do Teams Telehealth disponível no marketplace Do Marketplace.

## <a name="connector-setup"></a>Configuração do conector

A configuração do conector requer que você:

- [Iniciar o portal de configuração do Conector EHR](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [Informações de configuração](ehr-admin.md#configuration-information)
- [Aprovar ou exibir configuração](ehr-admin.md#approve-or-view-configuration)
- [Revisar e concluir a configuração](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[Iniciar o portal de configuração do Conector EHR](#launch-the-ehr-connector-configuration-portal)

Configurar sua organização de saúde para iniciar visitas virtuais com o Microsoft Teams começa iniciando o portal de configuração do EHR Connector. Configure uma ou várias organizações para testar a integração. Configure a URL de teste e produção no portal de configuração. Teste a integração do ambiente de teste da Epic antes de ir para a produção.
  
- URL de configuração do conector EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

O administrador do Microsoft 365 e o analista de clientes Dols de sua organização devem concluir as etapas de integração e informações no portal de configuração. Para ver as etapas de configuração doPico, entre em contato com o recurso especialista técnico Daaa atribuído à sua organização.

### <a name="configuration-information"></a>[Informações de configuração](#configuration-information)

Esta etapa deve ser concluída pelo administrador do **Microsoft 365.** O administrador do Microsoft 365 deve iniciar o portal de configuração do conector e entrar com credenciais da Microsoft para iniciar o processo de configuração.

Para concluir esta etapa, o administrador do Microsoft 365 deve receber uma URL de base FHIR (Recursos de Interoperabilidade de Saúde Rápida) válida do seu especialista técnico Do Microsoft 365 e o nome de usuário do analista de clientes Daltic que aprovará a configuração. O administrador do Microsoft 365 deve iniciar a página de configuração do conector e entrar com credenciais da Microsoft para iniciar o processo de configuração.

- A URL base FHIR é um endereço estático correspondente ao ponto de extremidade da API FHIR do servidor. Um exemplo de URL é `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` .

- O nome do aprovador de configuração é o nome do analista de clientes Dalmk, que será responsável por aprovar a configuração na próxima etapa. O analista de clientes Dalm é uma pessoa em sua organização com acesso de entrada aoPico.

  ![O nome do aprovador de configuração é selecionado em uma lista no conector EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[Aprovar ou exibir configuração](#approve-or-view-configuration)

O analista de clientes Dalt para sua organização de saúde que foi adicionado como aprovador agora deve usar a mesma URL do Conector EHR da etapa anterior para entrar usando suas credenciais do Microsoft 365. Após a validação bem-sucedida, o aprovador será solicitado a entrar usando suas credenciais de Aérea para validar a organização Doa.

> [!Note]
> O administrador do Microsoft 365 e o analista de clientes Dols em sua organização podem ser a mesma pessoa. Nesse caso, adicione seu próprio nome de usuário como aprovador. Você ainda precisará entrar noPico Para validar seu acesso. A assinatura do Élpico é usada apenas para validar sua URL base FHIR. A Microsoft não armazenará credenciais ou acessará dados de EHR com essa entrada.

  ![Verifique e aprove a configuração de credenciais.](../../media/approve-view-configuration.png)

Depois de uma entrada bem-sucedida da Aérea, o analista de clientes Dalmá **deve** aprovar a configuração. Se a configuração não estiver correta, o administrador do Microsoft 365 terá a capacidade de modificar as configurações originais ao entrar no portal do conector EHR da Microsoft novamente. 

![Confirme se o conector EHR está configurado e a opção para alterar a configuração.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[Revisar e concluir a configuração](#review-and-finish-the-configuration)

Quando as informações de configuração tiverem sido aprovadas pelo administrador do Programa, você será apresentado com registros de integração para o lançamento do paciente e do provedor. Esses registros são necessários para concluir a configuração de visita virtual noPico. Consulte o guia Epic-Microsoft Integração do Teams Telehealth para obter mais detalhes.

> [!Note]  
> A qualquer momento, o analista de clientes Do Microsoft 365 ou o analista de clientes Dols pode entrar no portal de configuração para exibir registros de integração e modificar a configuração da organização, se necessário.

![As informações de integração são exibidas.](../../media/finish-configuration.png)

> [!Note]
> O processo de aprovação deve ser concluído pelo analista de clientes DaLm para cada URL FHIR configurada pelo administrador da Microsoft antes.

![As informações de configuração são aprovadas.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Iniciar visitas virtuais do Teams

Depois de concluir as etapas do Conector EHR e a configuração dePico, sua organização está pronta para dar suporte a visitas com vídeo com o Microsoft Teams.

### <a name="virtual-visit-prerequisites"></a>Pré-requisitos de visita virtual

- Seus sistemas devem atender a [todos os pré-requisitos](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)de software e navegador.

- A organização de serviços de saúde deve ter concluído a configuração entre a organização do Microsoft 365 e a organização do Microsoft 365.

### <a name="provider-experience"></a>Experiência do provedor

Os provedores de saúde de sua organização também podem ingressar em visitas virtuais com o Microsoft Teams a partir de seus aplicativos de provedores Deslocados (Hyperspace, Vpnku, Canto). O **botão Iniciar visita virtual** é inserido no fluxo do provedor.

Principais recursos da experiência do provedor:

- Os provedores podem ingressar em visitas virtuais usando navegadores com suporte ou o aplicativo Microsoft Teams.

- Os provedores devem fazer uma logon única com sua conta do Microsoft 365 ao ingressar em uma visita virtual pela primeira vez.

- Após a logon única, o provedor será levado diretamente para o compromisso virtual no Microsoft Teams. (O provedor deve estar dentro do Microsoft Teams).

- O provedor pode ver atualizações em tempo real dos participantes se conectam e se desconectam para um determinado compromisso. O provedor pode ver quando o paciente está conectado a uma visita virtual.

  ![Experiência do provedor de uma visita virtual com o paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>Experiência do paciente

O conector dá suporte a pacientes in joining virtual visits through MyChart web and mobile. No momento do compromisso, os pacientes podem iniciar uma visita virtual a partir de Meu Gráfico usando o **botão Iniciar visita virtual.**

Principais recursos da experiência do paciente:

- Os pacientes podem ingressar em visitas virtuais a partir de navegadores da Web modernos na área de trabalho e em dispositivos móveis sem instalação de aplicativos.

- Os pacientes podem ingressar em visitas virtuais com um único clique e não há nenhuma outra conta ou necessidade de entrar.

- Os pacientes não são obrigados a criar uma conta da Microsoft ou entrar para iniciar uma visita virtual.

- Os pacientes serão colocados em um lobby até que o provedor de saúde in joins in the appointment and admits them to the virtual visit.

- O teste do vídeo e do microfone está disponível no lobby antes de ingressar na visita virtual.

  ![Experiência do paciente da visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Émúm, MyChart,Kuku e Canto são marcas registradas da Corporação Det.

### <a name="privacy-and-location-of-data"></a>Privacidade e localização dos dados

A integração do Teams aos sistemas de EHR otimiza a quantidade de dados que estão sendo usados e armazenados durante a integração e os fluxos de visitas virtuais. A solução segue os princípios gerais de privacidade e gerenciamento de dados do Teams e as diretrizes descritas na Privacidade do Teams.

O conector EHR do Microsoft Teams não armazena nem transfere dados pessoais identificáveis ou quaisquer registros de saúde de pacientes ou provedores de saúde do sistema EHR. Os únicos dados armazenados pelo conector EHR são a ID exclusiva do usuário do EHR, que é usada durante a configuração da reunião do Teams. A ID exclusiva do usuário do EHR é armazenada em uma das três regiões geográficas descritas em Onde seus dados de cliente do [Microsoft 365 são armazenados.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) Todos os chats, gravações e outros dados inseridos no Teams pelos participantes da reunião são armazenados de acordo com as políticas de armazenamento existentes. Se quiser saber mais sobre a localização dos dados no Microsoft Teams, visite [Locais de dados no Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)
