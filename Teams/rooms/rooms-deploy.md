---
title: Implantar Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber mais sobre como implantar Salas do Microsoft Teams, incluindo as fases de implantação.
ms.openlocfilehash: 9dbb45581467cb0f948ce7b5fb62dcfea1186918
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271776"
---
# <a name="deployment-overview"></a>Visão geral de implantação

A implantação Salas do Microsoft Teams é essencialmente dividido em fases:

- Confirmar que seus locais de implantação (espaços) atendem às dependências de implantação
- Criar contas do Microsoft Teams ou Skype for Business exchange e atribuí-las ao Salas do Teams (consulte [Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md))
- (Opcional) Configurando o Azure Monitor para seus sistemas (consulte [Implantar Salas do Microsoft Teams gerenciamento com o Azure Monitor](azure-monitor-deploy.md)
- Configurando Salas do Teams em espaços de reunião e conectando os dispositivos periféricos necessários (consulte a documentação do OEM para seu conjunto de dispositivos)

## <a name="site-readiness"></a>Preparação do site 

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com suas equipes de rede, instalações e AV para garantir que as dependências de implantação sejam atendidas e que cada site e espaço esteja pronto em termos de energia, rede e exibição. Além disso, verifique se os requisitos de instalação física foram atendidos. Para considerações sobre instalação física, consulte seu fornecedor e aproveite a experiência da sua equipe da AV ao instalar e montar telas e executar cabeamento.

Você pode saber mais sobre essas dependências nos links de diretrizes de planejamento abaixo:

-   [Verificar a disponibilidade da rede](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Dica pro** – se você precisar usar servidores proxy para fornecer acesso ao Teams, primeiro [examine este artigo](../proxy-servers-for-skype-for-business-online.md). Quando se trata do tráfego de mídia em tempo real do Microsoft Teams em servidores proxy, recomendamos ignorar completamente os servidores proxy. O tráfego do Microsoft Teams já está criptografado, portanto, os servidores proxy não o tornam mais seguro e adicionam latência ao tráfego em tempo real. Como parte de sua implantação mais ampla, recomendamos que você siga as diretrizes em Preparar sua rede para o [Teams](../prepare-network.md) para planejamento de largura de banda e avaliação da adequação da rede para tráfego em tempo real.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confirme sites.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos principais requisitos para Salas do Microsoft Teams.</li><li>Confirme se você forneceu largura de banda suficiente para cada site.</li></ul>| 
| ![planejar a implantação do dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração do dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontidão de serviço

Para se preparar para sua Salas do Microsoft Teams implantação, execute as seguintes tarefas centrais:

-   Defina Salas do Microsoft Teams de recursos.
-   Se você Salas do Teams ao Azure Active Directory, prepare um grupo de Azure AD com associação dinâmica para manter todas as contas de Salas do Teams recursos. Isso simplificará o gerenciamento futuro, como a aplicação de políticas de Acesso Condicional. Para aproveitar com mais facilidade Azure AD grupos dinâmicos, determine uma convenção de nomenclatura que identificará exclusivamente suas contas Salas do Teams recursos.
-   Se estiver ingressando no Salas do Teams para o Active Directory, prepare uma unidade organizacional e um grupo do Active Directory para manter suas contas de recursos e computadores do Salas do Microsoft Teams e, opcionalmente, preparar gpOs (objetos Política de Grupo) para habilitar a comunicação remota do PowerShell.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Definir recursos Salas do Microsoft Teams conta de recurso 

Dependendo dos cenários de colaboração que você decidiu habilitar com sua implantação do Salas do Microsoft Teams, você precisará determinar os recursos e os recursos atribuídos a cada Salas do Microsoft Teams que habilitar.

| **Cenário** | **Descrição** | **Salas do Microsoft Teams de conta de serviço** |
|---------- |------------- | --- |
| Reuniões interativas            | Usando compartilhamento de voz, vídeo e tela; tornando a Salas do Microsoft Teams um recurso acionável                     | Habilitado para o Microsoft Teams ou Skype for Business; habilitado para o Exchange (Caixa de Correio de Recursos) |
| Conferência discada            | Ter um número de telefone de audioconferência ao tocar em "Nova reunião" no console | Habilitado para Audioconferência                                          |
| Chamada PSTN de saída/entrada | Habilitar o console Salas do Microsoft Teams para fazer e receber chamadas PSTN                                         | Habilitado para Sistema de Telefonia                                                |

Para obter mais informações sobre Salas do Microsoft Teams contas, consulte [Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![suporte a cenários.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quais cenários você vai dar suporte e identifique os requisitos de licenciamento para suas contas Salas do Microsoft Teams recursos.</li></ul>| 
| ![preparar o computador host.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare-se para hospedar contas de recursos e computadores.</li></ul>| 


_Exemplo Salas do Microsoft Teams de planejamento da conta de recurso_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Recursos futuros da sala**                                                 | **Salas do Microsoft Teams da conta**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| QG de Londres | Curie         | Média        | 1 tela, áudio e vídeo mais apresentação <br>Acesso de conferência discada<br> Acesso PSTN  | Habilitado para o Exchange (Caixa de Correio de Recurso) <br>Habilitado para Audioconferência <br>Habilitado para Sistema de Telefonia |
| Sydney HQ | Hill          | Grande         | 2 Telas, áudio e vídeo mais apresentação<br>Acesso de conferência discada<br> Acesso PSTN  | Habilitado para Skype for Business <br>Habilitado para o Exchange (Caixa de Correio de Recurso)<br> Habilitado para Audioconferência <br>Habilitado para Sistema de Telefonia |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Preparar-se para hospedar Salas do Microsoft Teams contas de recursos (opcional)

Para permitir que você gerencie e relate suas contas de Salas do Microsoft Teams e recursos, prepare o Active Directory local ou o Azure Active Directory (Azure AD). 

Defina um Active Directory local ou grupo do Azure Active Directory ao qual adicionar todas as Salas do Microsoft Teams de recursos. Se estiver usando o Azure Active Directory, considere usar um grupo dinâmico para adicionar e remover automaticamente contas de recursos do grupo.

Defina uma unidade organizacional em sua hierarquia Active Directory local para manter todas as contas de computador do Salas do Microsoft Teams (se elas forem ingressadas no domínio) e uma unidade organizacional para armazenar todas as contas de Salas do Microsoft Teams usuário. Desabilite Política de Grupo herança para garantir que você aplique apenas as políticas que você pretendia aplicar ao grupo de Salas do Microsoft Teams.

Crie um Política de Grupo atribuído à unidade da organização que contém suas Salas do Microsoft Teams de computador. Use isso para: 

-   [Defina configurações de energia e conta local](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Habilite Windows Update.
-   Habilitar a comunicação remota do PowerShell. Você pode configurar um script de inicialização para executar um script: Enable-PSRemoting -Force

Você pode usar o PowerShell para executar várias atividades de gerenciamento remoto, incluindo obter e definir informações de configuração. A comunicação remota do PowerShell deve ser  habilitada antes que qualquer gerenciamento remoto do PowerShell possa ocorrer e deve ser considerada como parte de seus processos de implantação ou configurada por meio de Política de Grupo. Para obter mais informações sobre esses recursos e habilitá-los, consulte [Manutenção e operações](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuração e implantação 

O planejamento de configuração e implantação abrange as seguintes áreas principais:

-   Provisionamento de conta de recurso
-   Instalação de software do dispositivo
-   Implantação de dispositivo
-   Salas do Microsoft Teams aplicativo e configuração de dispositivo periférico
-    Testes
-   Gerenciamento de ativos

### <a name="resource-account-provisioning"></a>Provisionamento de conta de recurso 

Cada Salas do Microsoft Teams requer uma conta de recurso dedicada e exclusiva que deve ser habilitada para o Microsoft Teams ou Skype for Business e o Exchange. Essa conta deve ter uma caixa de correio de sala hospedada no Exchange. O processamento de calendário deve ser configurado para que o dispositivo possa aceitar automaticamente as solicitações de reunião de entrada. Para obter mais informações sobre como criar essas contas, consulte [Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md). 

**Dica Pro** – cada Salas do Microsoft Teams deve ter um nome de computador válido e exclusivo em sua rede. Muitos sistemas de monitoramento e alerta exibem o nome do computador como um identificador de chave, portanto, é importante desenvolver uma convenção de nomenclatura para implantações do Salas do Microsoft Teams que permite que a equipe de suporte localize facilmente o Salas do Microsoft Teams que foi sinalizado como exigindo uma ação. Um exemplo pode estar usando um padrão de *MTR-Site*-*Room Name* (MTR-LON-CURIE). 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![decidir convenção de nomenclatura.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenclatura para suas Salas do Microsoft Teams de recursos.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>| 
| ![próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalação de software do dispositivo 

Salas do Teams vem pré-instalado pelo OEM (fabricante original do equipamento).

Fornecemos diretrizes sobre como usar o [Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para monitorar a implantação do Salas do Microsoft Teams e relatar sobre disponibilidade, erros de hardware/software e Salas do Microsoft Teams do aplicativo. Se você decidir usar o Microsoft Operations Management Suite, instale o agente do Operations Management Suite como parte do processo de instalação de software e configure as informações de conexão do workspace para seu workspace. 

Uma consideração adicional é se o Salas do Microsoft Teams será ingressado no domínio. Informações sobre os benefícios de ingresso no domínio podem ser encontradas na configuração [Política de Grupo para Salas do Microsoft Teams](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms). 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![pontos de decisão de nomenclatura do dispositivo.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção Salas do Microsoft Teams de nomenclatura da conta de recurso a ser usada durante a implantação.</li><li>Decida se você ingressará Salas do Microsoft Teams dispositivos em seu domínio. </li><li>Decida se você usará o Azure Monitor para monitorar a Salas do Microsoft Teams implantação.</li> 
| ![as próximas etapas planejam o dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a abordagem de implantação do dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implantação de dispositivo

Depois de decidir como criar e gerenciar suas contas de recursos do Salas do Microsoft Teams, crie seu plano para enviar os dispositivos e seus periféricos atribuídos para suas salas e, em seguida, prossiga para a instalação e configuração.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![gerenciar a implantação site a site.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação site a site.</li><li> Identifique os recursos que instalarão o Salas do Microsoft Teams local e realizem a configuração e o teste.</li></ul>| 
| ![inicie o teste de dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste de dispositivo.</li></ul>| 

_Tabela de implantação de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Salas do Microsoft Teams sistema**  | **Dispositivos periféricos**  | **Salas do Microsoft Teams do computador**  | **Salas do Microsoft Teams de recursos**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| QG de Londres | Curie         | Média        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Salas do Microsoft Teams aplicativo e configuração de dispositivo periférico 

Depois que cada sistema Salas do Microsoft Teams tiver sido implantado fisicamente e os dispositivos periféricos com suporte conectados, você precisará configurar o aplicativo Salas do Microsoft Teams para atribuir a conta de recurso do Salas do Microsoft Teams e a senha para habilitar Salas do Teams entrar no Microsoft Teams ou no Skype for Business e no Exchange.

Você pode configurar manualmente cada Salas do Microsoft Teams sistema. Como alternativa, você pode usar um arquivo de configuração XML armazenado centralmente por Salas do Teams para gerenciar as configurações do aplicativo.

Para obter mais informações sobre como usar o arquivo de configuração XML, consulte [Gerenciar um Salas do Microsoft Teams de console remotamente com um arquivo de configuração XML](xml-config-file.md). 

Você pode usar [o PowerShell remoto](rooms-operations.md#remote-management-using-powershell) para efetuar pull da configuração Salas do Microsoft Teams para as necessidades de relatório. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configuração do ponto de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se você vai configurar manualmente cada sistema Salas do Microsoft Teams ou usar um arquivo XML central (um por Salas do Microsoft Teams dispositivo).</li></ul>| 
| ![próximas etapas de abordagem remota.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua abordagem de gerenciamento remoto.</li></ul>| 

### <a name="testing"></a> Testes

Depois Salas do Teams tiver sido implantado, você deve testá-lo. Verifique se os recursos listados [Salas do Microsoft Teams ajuda](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) estão funcionando no dispositivo implantado. É altamente recomendável que a equipe de implantação verifique se Salas do Microsoft Teams está aparecendo no Centro de administração do Teams. Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade. Para obter mais informações, consulte esta [lista de verificação de implantação útil](console.md#microsoft-teams-rooms-deployment-checklist).

Recomendamos que, como parte da distribuição geral do Teams ou do Skype for Business, você configure a criação de arquivos para o Painel de Qualidade de Chamadas (CQD), monitore as tendências de qualidade e participe do processo de Revisão de Qualidade da Experiência. Para obter mais informações, consulte [Melhorar e monitorar a qualidade das chamadas para o Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você desejará atualizar seu registro de ativo com o nome da sala, o nome Salas do Microsoft Teams, a conta de recurso Salas do Microsoft Teams e os dispositivos periféricos atribuídos. 

_Tabela de ativos de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Salas do Microsoft Teams serial no.**  | **Dispositivos periféricos/não serial./ Portas**  | **Salas do Microsoft Teams do computador**  | **Salas do Microsoft Teams de serviço**  | **Data da implantação** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| QG de Londres | Curie         | Média        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |
