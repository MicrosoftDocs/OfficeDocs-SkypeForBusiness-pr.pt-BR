---
title: Criar configurações de Qualidade de Experiência no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumo: Saiba mais sobre as configurações de QoE (Qualidade da Experiência) no Skype for Business Server.'
---

# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Criar configurações de Qualidade de Experiência no Skype for Business Server
 
**Resumo:** Saiba mais sobre as configurações de QoE (Qualidade da Experiência) em Skype for Business Server.
  
Os atributos métricos da Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "jitter" (diferenças no atraso de pacotes). Esses atributos métricos são armazenados em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação do QoE, independentemente de outros registros de dados.
  
Quando você instala Skype for Business Server, uma única coleção global de configurações de QoE é criada para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que estas configurações de escopo local são usadas, elas têm precedência sobre as configurações globais. Por exemplo, se você criar configurações com escopo de site para o site redmond, essas configurações (em vez das configurações globais) serão usadas para gerenciar a QoE em Redmond.
  
As configurações de QoE podem ser criadas usando o Painel de Controle Skype for Business Server ou o cmdlet [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps). Se você estiver usando Skype for Business Server Painel de Controle para criar novas configurações, as seguintes opções estarão disponíveis para você:
  
|**Configuração da interface do usuário**|**Parâmetro PowerShell**|**Descrição**|
|:-----|:-----|:-----|
|Nome  <br/> |Identidade  <br/> |Identificador exclusivo para as configurações a serem criadas. As configurações de QoE só podem ser criadas no escopo do site.  <br/> |
|Habilitar o monitoramento de dados QoE  <br/> |EnableQoE  <br/> |Especifica se os registros QoE serão coletados e salvos no banco de dados de monitoramento.  <br/> |
|Habilitar a purgação de dados QoE  <br/> |EnablePurging  <br/> |Especifica se os registros serão limpos após a duração definida na propriedade **Manter dados QoE por uma duração máxima (dias)** decorrido. <br/> |
|Manter dados QoE para duração máxima (dias)  <br/> |KeepQoEDataForDays  <br/> |O número de dias em que os dados de QoE serão armazenados antes de serem limpos do banco de dados. Esse valor será ignorado se a purgação estiver desabilitada.  <br/> |
   
> [!NOTE]
> O New-CsQoEConfiguration cmdlet inclui opções adicionais não disponíveis Skype for Business Server Painel de Controle. Para obter mais informações, consulte o [tópico de ajuda New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para criar configurações de QoE usando Skype for Business Server Painel de Controle

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Dados da Qualidade da Experiência**.
    
4. Na página **Qualidade dos Dados da Experiência** , clique em **Novo**.
    
5. Em **Selecionar um Site**, clique no site ao qual a política deve ser aplicada e clique em **OK**.
    
6. Em **Nova Configuração de Qualidade de Experiência**, faça o seguinte:
    
   - Selecione **Habilitar o monitoramento de dados QoE** para ativar o monitoramento.
    
   - Selecione **Habilitar a purgação de dados QoE** para ativar a purgação.
    
   - Em **Manter QoE por duração máxima (dias),** selecione o número máximo de dias em que os registros QoE devem ser mantidos.
    
7. Clique em **Confirmar**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando configuração de QoE Configurações usando Windows PowerShell cmdlets

Você pode criar configurações de QoE usando o Windows PowerShell e o cmdlet New-CsQoEConfiguration. Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Administração do Microsoft Lync Remote PowerShell](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para criar uma nova coleção de configurações de QoE

 Este comando cria uma nova coleção de definições de configuração de QoE aplicadas ao site redmond:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para criar uma nova coleção de configurações de QoE em que o monitoramento de QoE está desabilitado

 Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado. Por exemplo, para criar uma coleção de configurações de Qualidade de Experiência que, por padrão, permite desabilitar a gravação de QoE use um comando como este:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar vários valores de propriedade ao criar uma nova coleção de configurações de QoE

 Você pode vários valores de propriedade incluindo vários parâmetros. Por exemplo, este comando configura as novas configurações para manter os dados QoE por 30 dias e para limpar dados antigos às 3:00:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
