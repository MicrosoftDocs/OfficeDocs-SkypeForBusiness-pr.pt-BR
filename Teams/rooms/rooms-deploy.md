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
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber como implantar Salas do Microsoft Teams, incluindo as fases de implantação.
ms.openlocfilehash: 1f9edd4ccd2c0de00c91b99cef4f3f27b081b9ab
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015231"
---
# <a name="deployment-overview"></a>Visão geral de implantação

A implantação Salas do Microsoft Teams basicamente se divide em fases:

- Confirmando que seus locais de implantação (espaços) atendem às dependências de implantação
- Criando Microsoft Teams ou Skype for Business contas Exchange e atribuindo-as a Salas do Teams (consulte [Configure accounts for Salas do Microsoft Teams](rooms-configure-accounts.md))
- (Opcional) Configurando o Monitor do Azure para seus sistemas (consulte [Deploy Salas do Microsoft Teams management with Azure Monitor](azure-monitor-deploy.md)
- Configurando Salas do Teams espaços de reunião e conectando os dispositivos periféricos necessários (consulte a documentação do OEM para seu conjunto de dispositivos)

## <a name="site-readiness"></a>Preparação do site 

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com suas equipes de rede, instalações e AV para garantir que as dependências de implantação sejam atendidas e que cada site e espaço esteja pronto em termos de energia, rede e exibição. Além disso, certifique-se de que os requisitos de instalação física sejam atendidos. Para considerações sobre a instalação física, consulte seu fornecedor e aproveite a experiência da sua equipe av ao instalar e montar telas e executar o cabeamento.

Você pode saber mais sobre essas dependências nos links de orientação de planejamento abaixo:

-   [Verificar a disponibilidade da rede](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro Dica** - Se você precisa usar servidores proxy para fornecer acesso Teams, primeiro [revise este artigo](../proxy-servers-for-skype-for-business-online.md). Quando se trata de Microsoft Teams de mídia em tempo real por servidores proxy, recomendamos ignorar servidores proxy completamente. Microsoft Teams o tráfego já está criptografado, portanto, os servidores proxy não o torna mais seguro e adicionam latência ao tráfego em tempo real. Como parte de sua implantação mais ampla, recomendamos que você siga as diretrizes em [Preparar](../prepare-network.md) sua rede para o Teams para planejamento de largura de banda e avaliação da adequação da sua rede para tráfego em tempo real.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confirme sites.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos principais requisitos para Salas do Microsoft Teams.</li><li>Confirme se você forneceu largura de banda suficiente para cada site.</li></ul>| 
| ![planejar a implantação do dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração do dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontidão de serviço

Para se preparar para sua implantação Salas do Microsoft Teams, faça as seguintes tarefas centrais:

-   Defina Salas do Microsoft Teams de recursos.
-   Se ingressar no Teams Room para Azure Active Directory, prepare um grupo do Azure AD com associação dinâmica para manter todas as contas Salas do Teams recursos. Isso simplificará o gerenciamento futuro, como a aplicação de políticas de Acesso Condicional. Para aproveitar com mais facilidade os grupos dinâmicos do Azure AD, determine uma convenção de nomenização que identificará exclusivamente suas contas Salas do Teams recursos.
-   Se ingressar no Teams Room no Active Directory, prepare uma unidade organizacional e um grupo do Active Directory para manter suas contas de máquina e recursos do Salas do Microsoft Teams e, opcionalmente, preparar os objetos de Política de Grupo (GPOs) para habilitar o remoting do PowerShell.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Definir Salas do Microsoft Teams recursos de conta de recurso 

Dependendo dos cenários de colaboração que você decidiu habilitar com Salas do Microsoft Teams implantação do Salas do Microsoft Teams, você precisará determinar os recursos e recursos que você atribui a cada sala Microsoft Teams que você habilitar.

| **Cenário** | **Descrição** | **Salas do Microsoft Teams de conta de serviço** |
|---------- |------------- | --- |
| Reuniões interativas            | Usando compartilhamento de voz, vídeo e tela; tornando a Salas do Microsoft Teams um recurso bookable                     | Habilitado para Microsoft Teams ou Skype for Business; habilitado para Exchange (Caixa de Correio de Recursos) |
| Conferência discada            | Ter um número de telefone de audioconferência ao tocar em "Nova reunião" no console | Habilitado para Audioconferência                                          |
| Chamada PSTN de saída/entrada | Habilitar Salas do Microsoft Teams console para fazer e receber chamadas PSTN                                         | Habilitado para Sistema de Telefonia                                                |

Para obter mais informações sobre Salas do Microsoft Teams contas, consulte [Configure accounts for Salas do Microsoft Teams](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![suporte a cenários.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quais cenários você suportará e identifique os requisitos de licenciamento para suas contas Salas do Microsoft Teams de recursos.</li></ul>| 
| ![preparar a máquina host.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare-se para hospedar contas de recursos e máquinas.</li></ul>| 


_Exemplo Salas do Microsoft Teams de planejamento de conta de recurso_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Recursos de sala futuras**                                                 | **Salas do Microsoft Teams de conta**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| QG de Londres | Curie         | Média        | 1 tela, áudio e vídeo mais apresentação <br>Acesso de conferência discado<br> Acesso PSTN  | Habilitado para Exchange (Caixa de Correio de Recursos) <br>Habilitado para Audioconferência <br>Habilitado para Sistema de Telefonia |
| QG de Sydney | Monte          | Grande         | 2 Telas, áudio e vídeo mais apresentação<br>Acesso de conferência discado<br> Acesso PSTN  | Habilitado para Skype for Business <br>Habilitado para Exchange (Caixa de Correio de Recursos)<br> Habilitado para Audioconferência <br>Habilitado para Sistema de Telefonia |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Preparar para hospedar Salas do Microsoft Teams e contas de recursos (opcional)

Para permitir que você gerencie e reporte suas contas de Salas do Microsoft Teams e recursos, prepare o Active Directory local ou o Azure Active Directory (Azure AD). 

Defina um Active Directory local ou um grupo Azure Active Directory para adicionar todas as Salas do Microsoft Teams de recursos. Se estiver usando Azure Active Directory, considere usar um grupo dinâmico para adicionar e remover automaticamente contas de recursos do grupo.

Defina uma unidade organizacional em sua hierarquia local do Active Directory para manter todas as contas de máquina Salas do Microsoft Teams (se elas ingressarem no domínio) e uma unidade organizacional para manter todas as contas de Salas do Microsoft Teams de usuário. Desabilite a herança de Política de Grupo para garantir que você aplique apenas as políticas que você pretendia aplicar ao domínio ingressado Salas do Microsoft Teams.

Crie um objeto de Política de Grupo atribuído à unidade da organização que contém suas Salas do Microsoft Teams de computador. Use isso para: 

-   [Definir configurações de conta local e de energia.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Habilitar Windows Update.
-   Habilitar o remoting do PowerShell. Você pode configurar um script de início para executar um script: Enable-PSRemoting -Force

Você pode usar o PowerShell para executar várias atividades de gerenciamento remoto, incluindo obter e definir informações de configuração. O remoting do PowerShell deve ser habilitado antes que qualquer gerenciamento remoto do PowerShell possa ocorrer e deve ser considerado como parte de seus processos de implantação ou configurado por meio da Política de Grupo.  Para obter mais informações sobre esses recursos e habilita-los, consulte [Maintenance and operations](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuração e implantação 

O planejamento de configuração e implantação abrange as seguintes áreas principais:

-   Provisionamento de conta de recursos
-   Instalação de software de dispositivo
-   Implantação de dispositivo
-   Salas do Microsoft Teams aplicativo e configuração de dispositivo periférico
-    Testes
-   Gerenciamento de ativos

### <a name="resource-account-provisioning"></a>Provisionamento de conta de recursos 

Cada Salas do Microsoft Teams requer uma conta de recurso exclusiva e dedicada que deve ser habilitada para Microsoft Teams ou Skype for Business e Exchange. Essa conta deve ter uma caixa de correio de sala hospedada Exchange. O processamento de calendário deve ser configurado para que o dispositivo possa aceitar automaticamente solicitações de reunião de entrada. Para obter mais informações sobre como criar essas contas, consulte [Configure accounts for Salas do Microsoft Teams](rooms-configure-accounts.md). 

**Pro Dica** - Cada Salas do Microsoft Teams deve ter um nome de máquina válido e exclusivo em sua rede. Muitos sistemas de monitoramento e alerta exibem o nome do computador como um identificador de chave, portanto, é importante desenvolver uma convenção de nomenização para implantações do Salas do Microsoft Teams que permite que a equipe de suporte localize facilmente o Salas do Microsoft Teams que foi sinalizado como exigindo uma ação. Um exemplo pode estar usando um padrão de MTR-*Site* - *Room Name* (MTR-LON-CURIE). 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![decidir a convenção de nomenis.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenistura para suas Salas do Microsoft Teams de recursos.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>| 
| ![próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalação de software de dispositivo 

Salas do Teams vem pré-instalado pelo fabricante de equipamento original (OEM).

Fornecemos orientações sobre como usar o [Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para monitorar Salas do Microsoft Teams implantação e relatório sobre disponibilidade, erros de hardware/software e Salas do Microsoft Teams versão do aplicativo. Se você decidir usar o Microsoft Operations Management Suite, instale o agente do Operations Management Suite como parte do processo de instalação de software e configure as informações de conexão de espaço de trabalho para seu espaço de trabalho. 

Uma consideração adicional é se o Salas do Microsoft Teams será ingressado no domínio. Informações sobre os benefícios da junção de domínio podem ser encontradas em [Configuring Group Policy for Salas do Microsoft Teams](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms). 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![nomenis de dispositivo de pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a Salas do Microsoft Teams de nomenis de conta de recurso a ser usada durante sua implantação.</li><li>Decida se você ingressará Salas do Microsoft Teams dispositivos no seu domínio. </li><li>Decida se você usará o Monitor do Azure para monitorar a implantação Salas do Microsoft Teams usuário.</li> 
| ![próximas etapas planejam o dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar sua abordagem de implantação de dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implantação de dispositivo

Depois de decidir como criar e gerenciador suas contas de recursos Salas do Microsoft Teams, crie seu plano para enviar os dispositivos e seus periféricos atribuídos para suas salas e, em seguida, prossiga para a instalação e configuração.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![gerenciar a implantação site a site.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação site a site.</li><li> Identifique os recursos que instalarão Salas do Microsoft Teams local e realizar a configuração e o teste.</li></ul>| 
| ![iniciar o teste do dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste do dispositivo.</li></ul>| 

_Tabela de implantação de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Salas do Microsoft Teams sistema**  | **Dispositivos periféricos**  | **Salas do Microsoft Teams nome do computador**  | **Salas do Microsoft Teams de recurso**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| QG de Londres | Curie         | Média        |                                   |                  |                                          |                                             |
| QG de Sydney | Monte          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Salas do Microsoft Teams aplicativo e configuração de dispositivo periférico 

Depois que cada sistema Salas do Microsoft Teams tiver sido implantado fisicamente e os dispositivos periféricos com suporte conectados, você precisará configurar o aplicativo Salas do Microsoft Teams para atribuir a conta de recurso Salas do Microsoft Teams e a senha para habilitar Salas do Teams entrar no Microsoft Teams ou Skype for Business e Exchange.

Você pode configurar manualmente cada Salas do Microsoft Teams sistema. Como alternativa, você pode usar um arquivo de configuração XML armazenado centralmente por Salas do Teams para gerenciar as configurações do aplicativo.

Para obter mais informações sobre como usar o arquivo de configuração XML, consulte [Manage a Salas do Microsoft Teams console settings remotely with an XML configuration file](xml-config-file.md). 

Você pode usar [o PowerShell remoto](rooms-operations.md#remote-management-using-powershell) para puxar a configuração Salas do Microsoft Teams para necessidades de relatórios. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configuração do ponto de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se você configurará manualmente cada sistema Salas do Microsoft Teams ou usará um arquivo XML central (um por Salas do Microsoft Teams dispositivo).</li></ul>| 
| ![próximas etapas de abordagem remota.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua abordagem de gerenciamento remoto.</li></ul>| 

### <a name="testing"></a> Testes

Depois Salas do Teams tiver sido implantado, você deve testá-lo. Verifique se os recursos listados [Salas do Microsoft Teams ajuda estão](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) funcionando no dispositivo implantado. É altamente recomendável que a equipe de implantação verifique se Salas do Microsoft Teams está aparecendo no Teams de administração. Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade. Para obter mais informações, consulte esta [lista de verificação de implantação útil.](console.md#microsoft-teams-rooms-deployment-checklist)

Recomendamos que, como parte da Teams ou Skype for Business, você configure a criação de arquivos para o CQD (Painel de Qualidade de Chamada), monitore tendências de qualidade e participe do processo de Revisão da Qualidade da Experiência. Para obter mais informações, consulte [Improve and monitor call quality for Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você deseja atualizar seu registro de ativo com o nome da sala, Salas do Microsoft Teams nome, conta de recurso Salas do Microsoft Teams e dispositivos periféricos atribuídos. 

_Tabela de ativos de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Salas do Microsoft Teams serial no.**  | **Dispositivos periféricos/ Não serial./ Portas**  | **Salas do Microsoft Teams nome do computador**  | **Salas do Microsoft Teams de serviço**  | **Data implantada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| QG de Londres | Curie         | Média        |                                          |                                          |                                          |                                            |                   |
| QG de Sydney | Monte          | Grande         |                                          |                                          |                                          |                                            |                   |
