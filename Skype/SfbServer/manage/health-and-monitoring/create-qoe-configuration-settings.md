---
title: Criar definições de configuração de qualidade da experiência no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumo: Saiba mais sobre configurações de Quality of Experience (QoE) no Skype para Business Server.'
ms.openlocfilehash: 971d3488d0c6d20586e33424c1fbb2b197b31241
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198236"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Criar definições de configuração de qualidade da experiência no Skype para Business Server
 
**Resumo:** Saiba mais sobre configurações de Quality of Experience (QoE) no Skype para Business Server.
  
As métricas de Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de tremulação (diferenças no atraso de pacotes). Essas métricas são armazenadas em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação da QoE, independente de outros registros de dados.
  
Quando você instala o Skype para Business Server, uma única coleção global de definições de configuração de QoE é criada para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que essas configurações do escopo do site forem usadas, elas prevalecerão sobre as configurações globais. Por exemplo, se você criar configurações de escopo de site para o site da cidade de Redmond, essas configurações (em vez das globais) serão usadas para gerenciar a QoE em Redmond.
  
Configurações de QoE podem ser criadas usando qualquer um dos Skype para painel de controle do Business Server ou o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) . Se você estiver usando o Skype para painel de controle do Business Server para criar novas configurações as seguintes opções estarão disponíveis para você:
  
|**Configuração de interface do usuário**|**Parâmetro do PowerShell**|**Descrição**|
|:-----|:-----|:-----|
|Nome  <br/> |Identidade  <br/> |Identificador exclusivo das configurações a serem criadas. As configurações de QoE só podem ser criadas no escopo do site.  <br/> |
|Habilitar monitoramento de dados de QoE  <br/> |EnableQoE  <br/> |Especifica se os registros QoE serão coletados e salvos no banco de dados de monitoramento.  <br/> |
|Habilitar limpeza de dados de QoE  <br/> |EnablePurging  <br/> |Especifica se os registros serão apagados ao final do período definido na propriedade **Manter dados de QoE por um período máximo de (dias)**. <br/> |
|Manter dados de QoE por um período máximo de (dias)  <br/> |KeepQoEDataForDays  <br/> |O número de dias durante os quais os dados de QoE permanecerão armazenados antes de serem apagados do banco de dados. Esse valor será ignorado se a limpeza estiver desabilitada.  <br/> |
   
> [!NOTE]
> O cmdlet New-CsQoEConfiguration inclui opções adicionais não estão disponíveis no Skype para painel de controle do servidor de negócios. Para obter mais informações, consulte o tópico de Ajuda [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para criar definições de configuração de QoE usando Skype para o painel de controle do servidor de negócios

1. Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.
    
4. Na página **Dados de Qualidade da Experiência**, clique em **Novo**.
    
5. Em **Selecionar um site**, clique no site ao qual a política deverá ser aplicada e depois em **OK**.
    
6. Em **Criar Nova Configuração da Qualidade da Experiência**, faça o seguinte:
    
   - Selecione **Habilitar monitoramento de dados de QoE** para habilitar o monitoramento.
    
   - Selecione **Habilitar limpeza de dados de QoE** para habilitar a limpeza.
    
   - Em **Manter dados de QoE por um período máximo de (dias)**, selecione o número máximo de dias durante os quais os registros de QoE deverão ser mantidos.
    
7. Clique em **Confirmar**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando definições de configuração de QoE usando Cmdlets do Windows PowerShell

Você pode criar definições de configuração de QoE usando o Windows PowerShell e o cmdlet New-CsQoEConfiguration. Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para criar um novo conjunto de configurações de QoE

 Este comando cria um novo conjunto de configurações de QoE que será aplicado ao site de Redmond:
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para criar um conjunto de configurações de QoE com o monitoramento de QoE desabilitado

 Como nenhum parâmetro (além do parâmetro Identity obrigatório) foi especificado no comando anterior, o novo conjunto de configurações usará os valores padrão para todas as respectivas propriedades. Para criar configurações que usem outros valores de propriedade, basta incluir o parâmetro e o valor de parâmetro desejados. Por exemplo, para criar um conjunto de configurações de QoE que, por padrão, permita a desabilitação do registro de QoE, use um comando como o seguinte:
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar vários valores de propriedade ao criar um novo conjunto de configurações de QoE

 Você pode especificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, o seguinte comando define as novas configurações para manter os dados de QoE por 30 dias e para apagar os dados antigos às 3:00 AM:
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  

