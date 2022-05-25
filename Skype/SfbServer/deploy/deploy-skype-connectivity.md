---
title: Implantar Skype conectividade no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumo: saiba como se conectar Skype for Business Server com Skype consumidor. Também conhecido como Skype conectividade.'
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671677"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implantar Skype conectividade no Skype for Business Server

**Resumo:** Saiba como se conectar Skype for Business Server com Skype consumidor. Também conhecido como Skype conectividade.
  
Este artigo explica a implantação para Skype Conectividade.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype de conectividade para profissionais de TI

Skype conectividade fornece Skype for Business aos usuários com a capacidade de pesquisar e adicionar Skype usuários. Skype conectividade é um recurso do Skype for Business que permite habilitar a federação e a pesquisa de diretórios com Skype usuários. Depois de habilitar Skype conectividade, Skype for Business os usuários poderão pesquisar e adicionar Skype usuários.
  
## <a name="skype-directory-search"></a>Skype Pesquisa de Diretório

Skype de Pesquisa de Diretórios Skype for Business aos usuários com a capacidade de pesquisar Skype contatos. A funcionalidade de pesquisa permite que os usuários pesquisem usando o seguinte:
  
- **Pesquisar por nome de exibição, exemplo "John Doe"** – isso pode retornar muitos resultados, portanto, talvez você não encontre o que está procurando.
    
- **Pesquisar por nome de exibição mais local, exemplo "John Doe em Barcelona"** – Isso restringirá consideravelmente os resultados da pesquisa.
    
- **Pesquisar por email, exemplo "johndoe@outlook.com"** – isso deve retornar um resultado na maioria dos casos; aquele que corresponde exatamente ao email especificado. Mas se o mesmo email estiver associado a mais de uma conta, vários resultados poderão ser retornados.
    
- **Pesquisar por número de telefone, exemplo "123-123-1234"** – Isso deve retornar um resultado na maioria dos casos; aquele que corresponde exatamente ao telefone especificado. Telefone número deve incluir o código do país (ou seja, 1-xxx-aaa-zzzz). Se o mesmo número de telefone estiver associado a mais de uma conta, vários resultados poderão ser retornados.
    
- **Pesquisar por Skype Nome, exemplo "JohnDoe1456"** – Se a correspondência exata for encontrada, ela será retornada como o primeiro resultado. Outras possíveis partidas de "nome" podem ser retornadas.
    
    > [!NOTE]
    > Skype Directory Search deve ser capaz de se comunicar com os seguintes endereços IP na porta 443: 104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implantação com suporte para Skype Pesquisa de Diretório

A tabela a seguir descreve o suporte para Skype Pesquisa de Diretório.
  

|&nbsp;|Skype for Business Server front-end|Front-End do Lync Server 2013 (ou mais antigo)|Comentários|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge   |Com suporte   |Não Suportado   |Skype for Business Server e o Edge são pré-requisitos para a Skype Directory Search   |
|Skype for Business Server Edge + Lync Server 2013 Edge implantado lado a lado   |Com suporte   |Não Suportado   |Skype tráfego de Pesquisa de Diretório flui por Skype for Business Server de Borda. O tráfego de federação passa pela borda configurada pelo administrador. Por exemplo, o administrador pode optar por continuar a enviar tráfego de federação por meio de servidores de borda do Lync Server 2013 que não dão suporte Skype Directory Search.   |
|Lync Server 2013 (ou mais antigo) Edge   |Não Suportado   |Não Suportado   ||
   
> [!NOTE]
> O serviço de catálogo de endereços em execução Skype for Business Server Front-End localiza a borda pela existência da porta de pesquisa Skype 4443 no servidor de borda. 
  
> [!NOTE]
> Caso um cliente tenha vários sites em sua implantação local e se ele tiver implantado apenas um servidor/pool do Skype for Business Server Edge, o tráfego de pesquisa de todos os sites percorrerá o único servidor de borda disponível. O administrador precisa verificar se os pools de todos os sites podem acessar o servidor/pool Skype for Business Server Edge implantado. 
  
> [!NOTE]
> Skype serviço de grafo limitará as solicitações de pesquisa de qualquer cliente local ou Microsoft 365 ou Office 365 se a taxa de solicitação exceder 15 solicitações/segundo. 
  
> [!NOTE]
> Para clientes locais de grandes empresas, os domínios precisarão ser adicionados a uma lista de permitidos com o serviço de pesquisa Skype para permitir taxas de solicitação mais altas.
  
> [!NOTE]
> Skype for Business Server limitará as solicitações de entrada, se houver muitas solicitações pendentes na fila. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Implantando Skype conectividade para o Skype for Business Online

Skype conectividade também é um recurso do Skype for Business Online, que faz parte do Microsoft 365 e Office 365. Você pode habilitar o Skype de conectividade do Skype for Business De administração no Centro de administração do Microsoft 365.
  
Para Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education e Office 365 for Government: entre no Centro de administração do Microsoft 365 e navegue até o Centro Skype for Business Administração. Vá para Comunicações Externas. Em Provedores de Serviços de Mensagens Instantâneas Públicas, clique em Habilitar. Se você quiser controlar o acesso de usuário individual ao Skype Conectividade, poderá fazer isso editando as configurações de Comunicações Externas de usuários individuais.
  
Por Office 365 Small Business Premium: entre no Office 365 \> e vá para Administração serviço \> Configurações mensagens instantâneas, reuniões e conferências. Ativar comunicações externas. O comutador de comunicações externas ativa Skype conectividade e comunicações com outras organizações que usam Skype for Business.
  
Para obter mais informações sobre Skype for Business online, consulte:
  
- [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [O que tentar se você não puder enviar mensagens instantâneas Skype for Business ou Skype contatos externos](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Adicionar um contato no Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: definir Skype for Business configurações para usuários individuais](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implantando Skype conectividade para Skype for Business Server

Skype for Business Server usa a arquitetura de acesso de federação para dar suporte à conectividade com Skype. Essa conectividade permite que seus Skype for Business Server usuários adicionem Skype. Skype clientes também podem adicionar Skype for Business usuários à sua lista de contatos. Com base nas políticas definidas administrativamente Skype for Business Server os usuários poderão se comunicar usando mensagens instantâneas, ver a presença uns dos outros e iniciar chamadas de áudio e vídeo. Skype conectividade também é um recurso do Skype for Business Online e pode ser habilitada para clientes do Skype for Business Online no Centro de Administração do Skype for Business dentro do Centro de administração do Microsoft 365.
  
> [!NOTE]
> Se Skype for Business Server já estiver configurado para se conectar ao Windows Messenger usando a PIC (Conectividade de Mensagens Instantâneas Públicas), sua implantação já estará configurada para Skype conectividade. A única alteração que você pode querer considerar é renomear sua entrada de PIC do Messenger existente como Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>O Skype for Business Server de provisionamento de conectividade de mensagens instantâneas pública não está mais disponível

O site usado anteriormente para provisionar manualmente a federação entre implantações locais do Skype for Business e o Skype não é mais necessário e será desligado em 15/08/2019. A federação com Skype agora utiliza a descoberta de parceiros federados, que é o mesmo mecanismo necessário para federação com o Skype for Business Online.

A comunicação entre qualquer implantação Skype for Business local e usuários do Skype por meio da infraestrutura de mensagens instantâneas públicas existente agora requer que a configuração do Servidor de Borda local seja compatível com o Skype for Business Online.

> [!NOTE]
> Nenhuma ação é necessária para a maioria dos clientes, incluindo todas as implantações federadas com o Skype for Business Online.
  
Implantações locais são necessárias para publicar um registro SRV dns de federação para cada domínio que hospedam. As diretrizes estão disponíveis no [planejamento de DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Cada domínio deve ser resolvido por consulta DNS SRV para um FQDN de servidor de borda que satisfaça uma correspondência de sufixo de nível superior do domínio. Por exemplo, considere o domínio "contoso.com":

|**FQDNs válidos**|**Comentário**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |Em cada caso, o FQDN exato deve estar presente no SN ou na SAN do certificado externo instalado no servidor de borda.   |
|access.contoso.com   ||
|**FQDNs inválidos**|**Motivo**|
|sip.contoso-edge.com   |Não é uma correspondência de sufixo.  |
|sip.it.contoso.com   |Não é uma correspondência de sufixo de nível superior.   |

Outras diretrizes sobre certificados externos podem ser encontradas no [planejamento de certificados](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Perguntas frequentes

**Por que o site de provisionamento está sendo desligado?**
O mecanismo de provisionamento de IM pública (PIC) (pic.lync.com) implantado em 2006 não é mais serviceable e será desligado em 15/08/2019. Em vez disso, a federação de mensagens instantâneas públicas assumirá o mesmo modelo de federação usado pelo Skype for Business Online, conhecido como "descoberta de parceiros", em que uma implantação local é publicamente detectável por seus registros SRV dns de federação.

**Essa alteração significa que a federação de mensagens instantâneas públicas está sendo preterida?**
Não. A federação de mensagens instantâneas públicas continuará a ter suporte por muitos anos, provavelmente até que Skype for Business produto local atinja o fim da vida útil.

**Nossa empresa tem uma relação híbrida (espaço de endereço compartilhado) com o Skype for Business Online, somos afetados?**
Não, como você já está federando com o Skype for Business Online, essa alteração não afetará você.
 
**Essa alteração significa que nossa empresa precisa habilitar a federação com o Skype for Business Online?**
Não. Se as configurações de proxy do servidor de borda não habilitarem a federação com o provedor de hospedagem Skype for Business Online (sipfed.online.lync.com), essa alteração não afetará isso. No entanto, os mesmos requisitos de DNS e certificado que se aplicam à federação com o Skype for Business Online agora também se aplicam à federação com Skype usuários.
 
**Nossa empresa é grande e não pode alterar sua configuração de borda devido a motivos regulatórios/de conformidade/etc... O que podemos fazer?**
Qualquer organização local que não possa alterar sua configuração de servidor de borda, conforme especificado, deve entrar em contato com o suporte do produto na primeira oportunidade.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitando a federação e a PIC (conectividade de mensagens instantâneas públicas)

Agora, concentre-se no ambiente Skype for Business Server e nas tarefas administrativas necessárias para configurar Skype Conectividade. Nesta seção, presumimos que o administrador implantou Skype for Business Server e configurou o acesso externo, também conhecido como servidores de borda. 
  
Há três etapas principais necessárias para habilitar a federação e o PIC. São eles:
  
1. Configurar Federação e PIC
    
2. Configurar pelo menos uma política para dar suporte ao acesso de usuário federado
    
3. Definir a configuração Skype do provedor PIC
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar Federação e PIC

A federação é necessária para permitir que Skype usuários se comuniquem com Skype for Business usuários em sua organização. A PIC (Conectividade de Mensagens Instantâneas Públicas) é uma classe de federação e deve ser configurada para permitir que os usuários do Skype for Business se comuniquem com Skype usuários. A federação e o PIC são configurados usando o Skype for Business Server Painel de Controle.
  
> [!NOTE]
> A federação pic não tem mais suporte em versões de produto anteriores ao Lync Server 2010 (Live Communication Server, Office Communications Server). As plataformas com suporte para federação pic incluem Skype for Business Server, Lync Server 2013 e Lync Server 2010. 
  
A federação é necessária para permitir que Skype usuários se comuniquem com Skype for Business usuários em sua organização. A PIC (Conectividade de Mensagens Instantâneas Públicas) é uma classe de federação e deve ser configurada para permitir que os usuários do Skype for Business Server se comuniquem com Skype usuários. A federação e o PIC são configurados usando a caixa de diálogo de configuração do Edge do Skype for Business Server Painel de Controle conforme mostrado na figura.
  
![Defina o Novo Pool de Borda.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Os atributos EnableSkypeIdRouting e EnableSkypeDirectorySearch precisam ser definidos como true nas configurações do provedor público (consulte as instruções posteriores) para que a Pesquisa funcione. 
  
Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está configurado para Skype Conectividade.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configurar pelo menos uma política para dar suporte ao acesso de usuário federado

Usando o Skype for Business Server Painel de Controle, um administrador deve configurar uma ou mais políticas de acesso de usuário externo para controlar se Skype usuários podem colaborar com usuários Skype for Business Server internos.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Definir a configuração Skype provedor PIC

Usando o shell Skype for Business Server gerenciamento, um administrador deve configurar a política de cliente Skype for Business para exibir Skype como um provedor de PIC adicional. 
  
> [!NOTE]
> Os usuários dos provedores de serviços PIC (Conectividade de Mensagens Instantâneas Públicas) não poderão participar de mensagens instantâneas ou conferências em sua organização até que você também configure pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade de mensagens instantâneas públicas. 
  
Para novas instalações, você pode configurar Skype conectividade habilitando um provedor público Skype usando o Skype for Business Server Painel de Controle, conforme mostrado na figura.
  
![Provedores Federados SIP.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar Skype conectividade ao atualizar para Skype for Business Server você deve remover e adicionar novamente o provedor Skype existente. 
  
A configuração Skype conectividade também pode ser feita usando apenas o PowerShell. Para configurar Skype conectividade usando o PowerShell:
  
1. Em um Skype for Business Server Front-End, abra o Shell Skype for Business Server Gerenciamento.
    
2. Execute os dois comandos a seguir:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se você ainda não tiver um provedor PIC em seu ambiente e estiver criando um novo provedor de PIC, não precisará executar o cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    O que os parâmetros menos óbvios fazem?
    
   - ProxyFqdn: localização da Skype de federação (de propriedade/mantida pela Microsoft)
    
   - IconURL: ícone usado pelo Lync &amp; Skype for Business cliente para identificar visualmente Skype contatos
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: a configuração permite que os usuários insiram MSAs de usuários do Skype sem a necessidade de saber sobre "decorando" domínios que não são da Microsoft com "msn.com". Isso elimina a necessidade de digitar "user(contoso.com)@msn.com" para todos os domínios que NÃO estão na ExcludedDomainList. O cliente SfB formatará automaticamente a MSA se o domínio NÃO estiver na lista Excluídos. Adicionamos os domínios mais comuns da Conta da Microsoft à lista excluída.
    
     > [!NOTE]
     > O Provedor Público deve ser removido e adicionado novo se forem feitas alterações. Nenhuma alteração in-loco é permitida. 
  
     > [!NOTE]
     > Adicionado no cliente de área de trabalho do Lync Server 2013 CU5 &amp; Lync no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList melhoram a situação em que os usuários do Lync adicionando contatos do Skype necessários para "decorar" domínios não Microsoft para identificá-los e encaminhá-los para Skype (o formato de: user(contoso.com)@msn.com). Essas novas configurações permitirão a formatação automática da entrada do usuário do endereço na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser definido como msn.com) se ele não contiver os domínios no NameDecorationExcludedDomainList (atualmente, podemos dar suporte a msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Em um Skype for Business os usuários do cliente agora podem pesquisar e adicionar um Skype usuário.
    
## <a name="clients-and-interoperability-matrix"></a>Clientes e matriz de interoperabilidade

A tabela a seguir descreve o status da interoperabilidade entre a versão mais recente do Skype e a versão mais recente do Skype for Business.
  

|Skype clientes|Adicionar contatos, mensagens instantâneas, presença, áudio e chamadas de vídeo|Comentário|
|:-----|:-----|:-----|
|Skype Windows Desktop   |7.6 ou superior, Windows XP e superior   |**NOVO**: suporte adicionado para Windows Skype cliente em execução no Windows XP e no Windows Vista (requer a versão **mais recente do cliente 7.26 ou superior)**  |
|Skype Mobile – Android Telefone e Tablet   |6.19 ou superior, executando Android do sistema operacional versão 4.0.3 ou superior   |Dispositivos de baixa especificação podem não dar suporte à chamada de vídeo   |
|Skype Mobile – iOS   |6.11 ou superior, no IOS 7 ou superior   |Não há suporte para iPhone 4 e anteriores, iPod 4ª geração e versões anteriores, iPad 1ª geração   |
|Skype Mac   |7,19 ou superior, no Mac OS X 10.9 (Mavericks) ou superior   |Requer o Mac OSX 10.9 ou superior   |
|Skype Aplicativo Windows Universal (Windows 10) Desktop e Mobile   |Windows 10 (atualização do Redstone 1 ou posterior)   |Windows Aplicativo Universal receberá atualização no Outono de 2016 adicionando suporte à interoperabilidade   |
   
A tabela a seguir descreve o status da interoperabilidade entre a versão mais recente do Skype for Business e a versão mais recente do Skype consumidor. 
  
|Cliente|Skype Pesquisa de Diretório e Adicionar Contatos|Skype A/V, interoperabilidade de mensagens instantâneas|
|:-----|:-----|:-----|
|Skype for Business   |Sim   |Sim   |
|Skype for Business no Mac   |Pode adicionar (sem pesquisa)   |Sim   |
|Lync Desktop 2013   |Pode adicionar (sem pesquisa)   |Sim   |
|Lync Web App – online e local   |N/D   |N/D   |
|Lync Mobile – Windows Phone   |Em breve   |Sim   |
|Lync Mobile – Android   |Em breve   |Sim   |
|Lync Mobile – iOS   |Em breve   |Sim   |
|Sistema de salas do Lync   |Em breve   |Sim   |
|Aplicativo Moderno do Lync (Win 8.1)   |Sim   |Sim   |
|Lync Mac 2011   |Pode adicionar (sem pesquisa)   |Sim   |
|Lync Desktop 2010   |Pode adicionar (sem pesquisa)   |Sim   |
|Lync Phone Edition   |N/D   |N/D   |
|Atendedor do Lync   |N/D   |N/D   |
   
