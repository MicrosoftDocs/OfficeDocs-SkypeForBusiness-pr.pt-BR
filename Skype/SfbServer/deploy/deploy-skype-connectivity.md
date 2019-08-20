---
title: Implantar a conectividade do Skype no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumo: saiba como conectar o Skype for Business Server ao Skype consumidor. Também conhecida como conectividade com o Skype.'
ms.openlocfilehash: 4a335d2ec8e20310a34ce1bdfc8f39fe9b1117ee
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464596"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implantar a conectividade do Skype no Skype for Business Server

**Resumo:** Saiba como conectar o Skype for Business Server com o Skype Consumer. Também conhecida como conectividade com o Skype.
  
Este artigo apresenta o passo a passo da implantação da Conectividade Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Visão geral da Conectividade Skype para profissionais de TI

A conectividade do Skype oferece aos usuários do Skype for Business a capacidade de Pesquisar e adicionar usuários do Skype. A conectividade do Skype é um recurso do Skype for Business que permite habilitar a pesquisa de diretório e agrupamento com usuários do Skype. Depois de habilitar a conectividade do Skype, os usuários do Skype for Business poderão pesquisar e adicionar usuários do Skype.
  
## <a name="skype-directory-search"></a>Pesquisa de diretórios do Skype

A funcionalidade de pesquisa de diretórios do Skype permite que os usuários do Skype for Business pesquisem contatos do Skype. A funcionalidade de pesquisa permite que os usuários façam pesquisas usando as opções a seguir:
  
- **Pesquisar por nome para exibição, exemplo "John Doe"** -isso pode retornar muitos resultados, portanto, talvez você não encontre o que está procurando.
    
- **Pesquisar por nome para exibição e local, exemplo "John lemos em Barcelona"** -isso restringe consideravelmente os resultados da pesquisa.
    
- **Pesquisar por email, exemplo "johndoe@outlook.com"** -isso deve retornar um resultado na maioria dos casos; Aquele que corresponde exatamente ao e-mail especificado. Mas se o mesmo email estiver associado a mais de uma conta, vários resultados poderão ser retornados.
    
- **Pesquisar por número de telefone, exemplo "123-123-1234"** -isso deve retornar um resultado na maioria dos casos; Aquele que corresponde exatamente ao telefone especificado. O número de telefone deve incluir o código de país (por exemplo, 1-xxx-yyy-ZZZZ). Se o mesmo número de telefone estiver associado a mais de uma conta, vários resultados poderão ser retornados.
    
- **Pesquisar por nome Skype, exemplo "JohnDoe1456"** -se a correspondência exata for encontrada, ele será retornado como o primeiro resultado. Outras correspondências de "nome" possíveis podem ser retornadas.
    
    > [!NOTE]
    > A Pesquisa de Diretório do Skype deve ser capaz de se comunicar com os seguintes endereços IP na porta 443: 104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implantação suportada para a pesquisa de diretórios do Skype

A tabela a seguir apresenta o suporte para a pesquisa de diretórios do Skype.
  

||**Front-end do Skype for Business Server**|**Front-end do Lync Server 2013 (ou versões anteriores)**|**Comentários**|
|:-----|:-----|:-----|:-----|
|Borda do Skype for Business Server  <br/> |Com suporte  <br/> |Sem suporte  <br/> |O Skype for Business Server e o Edge são pré-requisitos para a pesquisa do diretório do Skype  <br/> |
|Skype for Business Server Edge + Lync Server 2013 Edge distribuído lado a lado  <br/> |Com suporte  <br/> |Sem suporte  <br/> |O tráfego da pesquisa de diretórios do Skype passa pelos servidores de borda do Skype for Business. O tráfego de federação passa pela borda configura pelo administrador. Por exemplo, o administrador pode optar por continuar a enviar o tráfego da federação por meio dos servidores de borda do Lync Server 2013, que não dão suporte à pesquisa de diretórios do Skype.  <br/> |
|Servidor de borda do Lync Server 2013 (ou anterior)  <br/> |Sem suporte  <br/> |Sem suporte  <br/> ||
   
> [!NOTE]
> O serviço agenda em execução no front-end do Skype for Business Server localiza a borda pela existência da porta 4443 de pesquisa do Skype no servidor de borda. 
  
> [!NOTE]
> Caso um cliente tenha vários sites na sua implantação local e, se eles implantarem apenas um servidor de borda/pool do Skype for Business Server, a pesquisa de tráfego de todos os sites passará pelo único servidor de borda disponível. O administrador precisa garantir que os pools de todos os sites possam acessar o servidor/pool de borda do Skype for Business Server implantado. 
  
> [!NOTE]
> O serviço de gráficos do Skype limitará as solicitações de pesquisa de clientes locais ou do Office 365 se a taxa de solicitações exceder 15 solicitações/segundo. 
  
> [!NOTE]
> Nos clientes corporativos de grande porte com implantações locais, os domínios deverão ser autorizados no serviço de pesquisa do Skype para aumentar as taxas de solicitações. 
  
> [!NOTE]
> O Skype for Business Server limitará as solicitações de entrada, se houver muitas solicitações pendentes na fila. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Implantando a Conectividade Skype para o Skype for Business Online no Office 365

O recurso Conectividade Skype também faz parte do Skype for Business Online, que, por sua vez, faz parte do Office 365. Você pode habilitar a Conectividade Skype por meio do Centro de Administração do Skype for Business no portal do Office 365.
  
Para o Office 365 Midsize Business, o Office 365 Enterprise, o Office 365 Education e o Office 365 for Government: entre no portal do Office 365 e navegue até o Centro de Administração do Skype for Business. Vá para Comunicações Externas. Em Provedores de Serviços Públicos de Mensagens Instantâneas, clique em Habilitar. Se quiser controlar o acesso de um usuário individual à conectividade do Skype, você pode fazer isso editando as configurações de comunicações externas de usuários individuais.
  
Para o Office 365 Small Business Premium: entrar no Office 365 e vá para configurações \> \> do serviço de administração, reuniões e conferências. Ative as comunicações internas. As comunicações externas são ativadas na Conectividade Skype e nas comunicações com outras organizações que usam o Skype for Business.
  
Para obter mais informações sobre a administração do Skype for Business Online, consulte:
  
- [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [O que tentar se não for possível enviar mensagens instantâneas para contatos externos do Skype for Business ou Skype](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Adicionar um contato no Skype for Business](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: Definir as configurações do Skype for Business para usuários individuais](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implantando a conectividade do Skype para o Skype for Business Server

O Skype for Business Server usa a arquitetura de acesso à Federação para dar suporte à conectividade com o Skype. Essa conectividade permite que seus usuários do Skype for Business Server adicionem contatos do Skype. Os clientes do Skype também podem adicionar usuários do Skype for Business a suas listas de contatos. Com base nas políticas definidas administrativamente nos usuários do Skype for Business Server, poderão se comunicar usando mensagens instantâneas, ver a presença das outras e iniciar chamadas de áudio e vídeo. O recurso Conectividade Skype também está disponível no Skype for Business Online e pode ser habilitado para clientes do Centro de Administração do Skype for Business no portal do Office 365.
  
> [!NOTE]
> Se o Skype for Business Server já estiver configurado para conectar-se ao Windows Messenger usando PIC (conectividade a redes públicas de mensagens instantâneas), sua implantação já está configurada para a Conectividade Skype. A única mudança que você pode considerar é renomear sua entrada existente de PIC no Messenger como Skype.  
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>O site de configuração de conectividade de mensagens instantâneas públicas do Skype for Business Server não está mais disponível

O site que antes era usado para provisionar manualmente a Federação entre implantações locais do Skype for Business e o Skype não é mais necessário e será desligado no 8/15/2019. A Federação com o Skype agora usa a descoberta de parceiro federado, que é o mesmo mecanismo necessário para federação com o Skype for Business online.

A comunicação entre qualquer implantação local do Skype for Business e usuários do Skype por meio da atual infraestrutura de IM existente agora requer que a configuração do servidor de borda local seja compatível com o Skype for Business online.

> [!NOTE]
> Nenhuma ação é necessária para a maioria dos clientes, incluindo todas as implantações que se agrupam com o Skype for Business online.
  
Implantações locais são necessárias para publicar um registro SRV DNS de Federação para cada domínio que eles hospedam. As diretrizes estão disponíveis no [planejamento de DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Cada domínio deve ser resolvido pela consulta SRV DNS para um FQDN do servidor de borda que satisfaça a correspondência de sufixo de nível superior do domínio. Por exemplo, considere o domínio "contoso.com":

|**FQDNs válidos**|**Comentário**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |Em cada caso, o FQDN exato deve estar presente na opção SN ou SAN do certificado externo instalado no servidor de borda.   |
|access.contoso.com   ||
|**FQDNs inválidos**|**Motivo**|
|sip.contoso-edge.com   |Não é uma correspondência de sufixo.  |
|sip.it.contoso.com   |Não há correspondência de sufixo de nível superior.   |

Diretrizes adicionais sobre certificados externos podem ser encontradas no [planejamento de certificado](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Freqüente

**Por que o site de provisionamento está sendo desligado?**
O mecanismo de provisionamento do sistema de mensagens de chat (PIC) pública (PIC) que foi implantado no 2006 não é mais útil e será desligado no 8/15/2019. Em vez disso, a Federação de mensagem de chat pública presumirá o mesmo modelo de Federação usado pelo Skype for Business Online, conhecido como "descoberta de parceiro", no qual uma implantação local é divulgada publicamente pelo (s) registro (s) SRV DNS de Federação.

**Essa alteração significa que a Federação de mensagem instantânea pública está sendo preterida?**
Não. A Federação de mensagem de chat pública continuará disponível por muitos anos, provavelmente até que o produto do Skype for Business no local atinja o fim da vida útil.

**Nossa empresa tem uma relação híbrida (espaço de endereço compartilhado) com o Skype for Business Online, estamos afetados?**
Não, como você já está se agrupando com o Skype for Business Online, essa alteração não irá afetá-lo.
 
**Essa alteração significa que nossa empresa tem de habilitar a Federação com o Skype for Business Online?**
Não. Se as configurações de proxy do servidor de borda não habilitarem Federação com o provedor de hospedagem do Skype for Business online (sipfed.online.lync.com), essa alteração não afetará isso. No entanto, os mesmos requisitos de DNS e certificado que se aplicam à Federação com o Skype for Business online agora também se aplicam à Federação com usuários do Skype.
 
**Nossa empresa é grande e não pode mudar sua configuração de borda devido a razões legais/de conformidade/etc... o que podemos fazer?**
Qualquer organização local que não pode alterar a configuração do servidor de borda conforme especificado deve entrar em contato com o suporte ao produto da primeira oportunidade.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitando a federação e a PIC

Agora, concentre-se no ambiente do Skype for Business e nas tarefas administrativas necessárias para configurar a conectividade com o Skype. Nesta seção, presumimos que o administrador implantou o Skype for Business Server e configurou o acesso externo, também conhecido como servidores de borda. 
  
Há três etapas principais necessárias para habilitar a federação e a PIC. São elas:
  
1. Configurar a federação e a PIC
    
2. Configurar pelo menos uma política para dar suporte ao acesso de usuários federados
    
3. Configurar a definição do provedor de PIC do Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar a federação e a PIC

A federação é necessária para permitir que os usuários do Skype se comuniquem com os usuários do Skype for Business em sua organização. A PIC é uma classe de federação e deve ser configurada para permitir que seus usuários do Skype for Business se comuniquem com os usuários do Skype. A federação e a PIC são configuradas por meio do Painel de Controle do Skype for Business.
  
> [!NOTE]
> A Federação de PIC não é mais suportada por versões de produto anteriores ao Lync Server 2010 (Live Communication Server, Office Communications Server). As plataformas com suporte para a Federação PIC incluem Skype for Business Server, Lync Server 2013 e Lync Server 2010. 
  
A federação é necessária para permitir que os usuários do Skype se comuniquem com os usuários do Skype for Business em sua organização. A PIC é uma classe de federação e deve ser configurada para permitir que seus usuários do Skype for Business Server se comuniquem com os usuários do Skype. A federação e a PIC são configuradas por meio da caixa de diálogo de configuração de borda do Painel de Controle do Skype for Business, conforme mostra a figura.
  
![Definir novo pool de bordas](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Os atributos EnableSkypeIdRouting e EnableSkypeDirectorySearch devem ser definidos como true nas configurações de provedor público (consulte as instruções mais adiante) para que a pesquisa funcione. 
  
Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está pronto para a Conectividade Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configure pelo menos uma política para dar suporte ao acesso de usuário federado

Usando o Painel de Controle do Skype for Business Server, o administrador deve configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários do Skype podem colaborar com usuários internos do Skype for Business Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurar a configuração do provedor de PIC do Skype

Usando o Shell de Gerenciamento do Skype for Business Server, o administrador deve configurar a política de cliente do Skype for Business para exibir o Skype como um provedor de PIC adicional.  
  
> [!NOTE]
> Os usuários dos provedores de serviços públicos de conexão de mensagens instantâneas (PIC) não podem participar de mensagens instantâneas ou conferências em sua organização até você também configurar pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade de IM pública. 
  
Para novas instalações, você pode configurar a Conectividade Skype ao habilitar o provedor público do Skype, por meio do Painel de Controle do Skype for Business Server, conforme mostra a figura.
  
![Provedores Federados SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar a Conectividade Skype ao atualizar para o Skype for Business Server, você deve remover o provedor público existente do Skype e adicioná-lo novamente. 
  
Também é possível configurar a Conectividade Skype usando somente o PowerShell. Para configurar a Conectividade Skype usando o PowerShell:
  
1. Em um servidor front-end do Skype for Business Server, abra o Shell de Gerenciamento do Skype for Business Server.
    
2. Execute estes dois comandos:
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se você ainda não tem um provedor de PIC em seu ambiente e está criando um novo provedor de PIC, não é necessário executar o cmdlet Remove-CsPublicProvider.  
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Qual é a função dos parâmetros menos óbvios?
    
   - ProxyFqdn: localização da borda de federação do Skype (própria/mantida pela Microsoft)
    
   - IconURL: ícone usado pelo cliente &amp; do Lync Skype for Business para identificar visualmente os contatos do Skype
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: a configuração desses usuários permite que os usuários insiram o MSAs de usuários do Skype sem precisar saber sobre o "decoração" de domínios que não sejam da Microsoft com "msn.com". Isso elimina a necessidade de digitar "usuário (contoso. com) @msn. com" para todos os domínios que não estão no ExcludedDomainList. O cliente SfB formatará automaticamente o MSA se o domínio NÃO estiver na lista de exclusões. Adicionamos os domínios de conta da Microsoft mais comuns à lista excluída.
    
     > [!NOTE]
     > Em caso de alterações, o provedor público deverá ser removido e um novo provedor deverá ser adicionado. Não é permitido fazer alterações in-loco. 
  
     > [!NOTE]
     > Adicionado ao Lync Server 2013 CU5 &amp; o cliente de área de trabalho Lync no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList melhoram a situação em que os usuários do Lync adicionam contatos do Skype necessários para "decorar" domínios que não sejam da Microsoft Identifique e encaminhe-os para o Skype (o formato de: usuário (contoso. com) @msn. com). Essas novas configurações permitirão a formatação automática da entrada do usuário do endereço na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser definido como msn.com) se ele não contiver os domínios no NameDecorationExcludedDomainList ( Atualmente, podemos dar suporte a msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Agora, a partir de um cliente Skype for Business, os usuários podem pesquisar e adicionar usuários do Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Clientes e matriz de interoperabilidade

A tabela a seguir descreve o status de interoperabilidade entre a versão mais recente do consumidor do Skype e a versão mais recente do Skype for Business.
  

|**Clientes Skype**|**Adicionar contatos, IM, presença, chamada de áudio e vídeo**|**Comentário**|
|:-----|:-----|:-----|
|Skype Windows Desktop  <br/> |7.6 ou superior, Windows XP ou superior  <br/> |**Novo**: suporte adicionado para o cliente Windows Skype em execução no Windows XP e Windows Vista **(requer a versão mais recente do cliente 7,26 ou superior)** <br/> |
|Skype Mobile- telefone Android e Tablet   <br/> |6.19 ou superior, executando o Sistema Operacional do Android versão 4.0.3 ou superior  <br/> |Dispositivos de baixa especificação podem não suportar chamada de vídeo  <br/> |
|Skype Mobile-iOS  <br/> |6.11 ou superior, em IOS 7 ou superior  <br/> |Não compatível com iPhone 4 e anteriores, iPod quarta geração e anteriores, iPad primeira geração  <br/> |
|Skype Mac  <br/> |7.19 ou superior, no Mac OS X 10.9 (Mavericks) ou superior  <br/> |Requer Mac OSX 10.9 ou superior  <br/> |
|Área de trabalho e celular do Aplicativo Universal Windows para Skype (Windows 10)  <br/> |Windows 10 (Redstone 1 atualizado ou posterior)  <br/> |O aplicativo universal do Windows receberá uma atualização no terceiro trimestre de 2016, quando será adicionado suporte para interoperabilidade  <br/> |
   
A tabela a seguir descreve o status de interoperabilidade entre a versão mais recente do Skype for Business e a versão mais recente do consumidor do Skype.  
  
|**Cliente**|**Pesquisa de diretórios do Skype e Adicionar contatos**|**Interop de áudio e vídeo e mensagens instantâneas do Skype**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Sim   <br/> |Sim   <br/> |
|Skype for Business para Mac  <br/> |É possível adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Desktop 2013  <br/> |É possível adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Web App – online e local  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile – Windows Phone  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Mobile – Android  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Mobile – iOS  <br/> |Em breve  <br/> |Sim  <br/> |
|Sistema de Salas do Lync  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Sim  <br/> |Sim   <br/> |
|Lync Mac 2011  <br/> |É possível adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Desktop 2010  <br/> |É possível adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/D  <br/> |N/D  <br/> |
   

