---
title: Configurar um controlador de borda da sessão para vários locatários
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Saiba como configurar um SBC (controlador de borda de sessão) para atender a vários locatários.
ms.openlocfilehash: c759e80796397b9b1d7606277c8f834c83d7e8e7
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821066"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurar um controlador de borda da sessão para vários locatários

O roteamento direto suporta a configuração de um SBC (controlador de borda de sessão) para atender a vários locatários.

> [!NOTE]
> Esse cenário foi projetado para operadoras de parceiros da Microsoft e/ou PSTN, conhecidos como transportadoras mais adiante neste documento. Uma operadora vende serviços de telefonia entregues ao Microsoft Teams para seus clientes. 

Uma operadora:
- Implanta e gerencia um SBC em seu datacenter (os clientes não precisam implementar um SBC e eles recebem serviços de telefonia da operadora no cliente do Teams).
- Interconecta o SBC a vários locatários.
- Fornece serviços PSTN aos clientes.
- Gerencia a qualidade da chamada de ponta a ponta.
- Cobranças separadamente para serviços PSTN.

A Microsoft não gerencia operadoras. A Microsoft oferece um PBX (Microsoft Phone System) e um cliente do Teams, certifica telefones e certifica SBCs que podem ser usados com o sistema telefônico da Microsoft. Antes de escolher uma operadora, certifique-se de que sua escolha tem um SBC certificado e pode gerenciar a qualidade de voz de ponta a ponta.

Veja a seguir as etapas de implementação técnica para configurar o cenário.

**Somente portadora:**
1. Implante o SBC e configure-o para o cenário de Hospedagem de acordo com as [instruções dos fornecedores de SBC certificados](#deploy-and-configure-the-sbc).
2. Registre um nome de domínio base no locatário da operadora e solicite um certificado curinga.
3. Registre um subdomínio para cada cliente, que faz parte do domínio base.

**Operadora com um administrador global do cliente:**
1. Adicione o nome de subdomínio ao locatário do cliente.
2. Ativar o nome do subdomínio.
3. Configure o tronco da transportadora para o locatário do cliente e provisionar usuários.

*Certifique-se de compreender noções básicas de DNS e como o nome de domínio é gerenciado no Office 365. Examine [a ajuda para obter ajuda com os domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) antes de continuar.*

## <a name="deploy-and-configure-the-sbc"></a>Implantar e configurar o SBC

Para ver as etapas detalhadas sobre como implantar e configurar o SBCs para um cenário de hospedagem SBC, consulte a documentação do fornecedor do SBC.

- **AudioCodes:** [Rotas diretas de configuração de roteamento](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), a configuração do cenário de Hospedagem de SBC descrito em "conectando AudioCodes SBC para a Microsoft Teams Direct Routing Host Configuration model observação". 
- **Comunicações da faixa** de opções:  Consulte o guia de [configuração do Microsoft Teams SBC da faixa](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) de opções do Microsoft Teams para obter a documentação sobre como configurar a faixa de opções da faixa de opções SBCS e para esta página de [práticas recomendadas-configurando as operadoras do Microsoft Teams Direct Margem](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)

> [!NOTE]
> Preste atenção em como configurar o cabeçalho "contato". O cabeçalho do contato é usado para localizar o locatário do cliente na mensagem de convite de entrada. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrar um domínio base e subdomínios

Para o cenário de hospedagem, você precisa criar:
- Um nome de domínio base pertencente à transportadora.
- Um subdomínio que faz parte do nome do domínio base em cada locatário do cliente.

No exemplo a seguir:
- Adatum é uma operadora que atende vários clientes fornecendo serviços de telefonia e de Internet.
- Woodgrove Bank, contoso e Adventure Works são três clientes que têm domínios do Office 365, mas recebem os serviços de telefonia do adatum.

Subdomínios **devem** coincidir com o nome FQDN do tronco que será configurado para o cliente e o FQDN no cabeçalho do contato ao enviar o convite para o Office 365. 

Quando chega uma chamada na interface de roteamento direto do Office 365, a interface usa o cabeçalho do contato para localizar o locatário onde o usuário deve ser pesquisado. O roteamento direto não usa a pesquisa de número de telefone no convite, pois alguns clientes podem ter números não-participantes que podem sobrepor-se a vários locatários. Portanto, o nome FQDN no cabeçalho do contato é necessário para identificar o locatário exato para pesquisar o usuário pelo número de telefone.

*Consulte [obter ajuda com os domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como criar nomes de domínio nos locatários do Office 365.*

O diagrama a seguir resume os requisitos para o domínio base, subdomínios e cabeçalho de contato.

![Diagrama mostrando os requisitos para domínios e cabeçalho de contato](media/direct-routing-1-sbc-requirements.png)

O SBC exige um certificado para autenticar as conexões. Para o cenário de hospedagem SBC, a transportadora precisa solicitar um certificado com San * \*. base_domain (por \*exemplo, Customers.adatum.biz)*. Esse certificado pode ser usado para autenticar conexões para vários locatários servidos a partir de um único SBC.

A tabela a seguir é um exemplo de uma configuração.


|Novo nome de domínio |Tipo|Removido  |SAN de certificado para SBC  |Domínio padrão do locatário no exemplo  |Nome FQDN que o SBC deve apresentar no cabeçalho do contato ao enviar chamadas para usuários|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Polybase     |     No locatário da operadora  |    \*. customers.adatum.biz  |   adatum.biz      |No, este é um locatário de serviço, nenhum usuário |
|sbc1.customers.adatum.biz|    Subdomínio  |    Em um locatário do cliente  |    \*. customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomínio | Em um locatário do cliente   |   \*. customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomínio | Em um locatário do cliente |   \*. customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Para configurar a base e subdomínios, siga as etapas descritas abaixo. No exemplo, configuraremos um nome de domínio base (customers.adatum.biz) e um subdomínio para um cliente (sbc1.customers.adatum.biz no locatário do Woodgrove Bank).

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrar um nome de domínio base no locatário da operadora

**Essas ações são executadas no locatário da operadora.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Certifique-se de ter os direitos apropriados no locatário da operadora

Você só poderá adicionar novos domínios se tiver entrado no centro de administração do Microsoft 365 como administrador global. 

Para validar a função que você tem, entre no centro de administração do Microsoft 365 (https://portal.office.com), vá para **** > usuários**ativos**do Microsoft e verifique se você tem uma função de administrador global. 

Para obter mais informações sobre funções de administrador e como atribuir uma função no Office 365, consulte [sobre as funções de administrador do office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Adicionar um domínio base ao locatário e verificá-lo

1.  No centro de administração do Microsoft 365, vá para **Configurar** > **domínios** > **Adicionar domínio**.
2.  Na caixa **Insira um domínio que você possui** , digite o FQDN do domínio base. No exemplo a seguir, o domínio base é *Customers.adatum.biz*.

    ![Captura de tela mostrando a página Adicionar um domínio](media/direct-routing-2-sbc-add-domain.png)

3. Click **Next**.
4. No exemplo, o locatário já tem adatum.biz como um nome de domínio verificado. O assistente não solicitará verificação adicional, pois customers.adatum.biz é um subdomínio para o nome já registrado. No entanto, se você adicionar um FQDN que não tenha sido verificado antes, será necessário passar pelo processo de verificação. O processo de verificação está [descrito abaixo](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Captura de tela mostrando a confirmação de um nome de domínio verificado](media/direct-routing-3-sbc-verify-domain.png)

5.  Clique em **Avançar**e, na página **Atualizar configurações de DNS** , selecione **eu mesmo adiciono os registros DNS** e clique em **Avançar**.
6.  Na próxima página, desmarque todos os valores (a menos que você queira usar o nome do domínio do Exchange, do SharePoint ou do teams/Skype for Business), clique em **Avançar**e, em seguida, clique em **concluir**. Verifique se o novo domínio está no status de configuração concluída.

    ![Captura de tela mostrando domínios com status de configuração concluída](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Ativar o nome de domínio

Depois de registrar um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário licenciado E1, E3 ou E5 e atribuindo um endereço SIP à parte FQDN do endereço SIP correspondente ao domínio base criado. 

*Consulte [obter ajuda com os domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como adicionar usuários nos locatários do Office 365.*

Por exemplo: test@customers.adatum.biz

![Captura de tela da página de ativação de domínio base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrar um nome de subdomínio em um locatário do cliente

Será necessário criar um nome de subdomínio exclusivo para cada cliente. Neste exemplo, criaremos um subdomínio sbc1.customers.adatum.biz em um locatário com o nome de domínio padrão woodgrovebank.us.

**Todas as ações abaixo estão no locatário do cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Certifique-se de ter os direitos apropriados no locatário do cliente

Você só poderá adicionar novos domínios se tiver entrado no centro de administração do Microsoft 365 como administrador global. 

Para validar a função que você tem, entre no centro de administração do Microsoft 365 (https://portal.office.com), vá para **** > usuários**ativos**do Microsoft e verifique se você tem uma função de administrador global. 

Para obter mais informações sobre funções de administrador e como atribuir uma função no Office 365, consulte [sobre as funções de administrador do office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Adicionar um subdomínio ao locatário do cliente e verificá-lo
1. No centro de administração do Microsoft 365, vá para **Configurar** > **domínios** > **Adicionar domínio**.
2. Na caixa **Insira um domínio que você possui** , digite o FQDN do subdomínio para esse locatário. No exemplo a seguir, o subdomínio é sbc1.customers.adatum.biz.

    ![Captura de tela da página Adicionar um domínio](media/direct-routing-5-sbc-add-customer-domain.png)

3. Click **Next**.
4. O FQDN nunca foi registrado no locatário. Na próxima etapa, será necessário verificar o domínio. **Em vez disso, selecione Adicionar um registro txt**. 

    ![Captura de tela da página verificar domínio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Clique em **Avançar**e observe o valor txt gerado para verificar o nome do domínio.

    ![Captura de tela de registros de texto na página verificar domínio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Crie o registro TXT com o valor da etapa anterior no provedor de Hospedagem de DNS da transportadora.

    ![Captura de tela mostrando a criação do registro TXT](media/direct-routing-8-sbc-txt-record.png)

    Para obter mais informações, consulte [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Volte para o centro de administração do Microsoft 365 do cliente e clique em **verificar**. 
8. Na próxima página, selecione **adicionarei os registros de DNS** e clique em **Avançar**.

    ![Captura de tela das opções na página atualizar configurações de DNS](media/direct-routing-9-sbc-update-dns.png)

9. Na página **escolher seus serviços online** , desmarque todas as opções e clique em **Avançar**.

    ![Captura de tela da página escolher seus serviços online](media/direct-routing-10-sbc-choose-services.png)

10. Clique em **concluir** na página **Atualizar configurações de DNS** .

    ![Captura de tela da página atualizar configurações de DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Certifique-se de que o status seja **configuração concluído**. 
    
    ![Captura de tela da página mostrando o status da configuração concluída](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Ativar o nome do subdomínio

Depois de registrar um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário e atribuir um endereço SIP à parte FQDN do endereço SIP correspondente ao subdomínio criado no locatário do cliente.

*Consulte [obter ajuda com os domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como adicionar usuários nos locatários do Office 365.*

Por exemplo: test@sbc1.customers.adatum.biz

![Captura de tela da ativação da página de subdomínio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Criar um tronco e provisionar usuários

Com a versão inicial do roteamento direto, a Microsoft exigia que um tronco fosse adicionado a cada locatário servido (locatário do cliente) usando New-CSOnlinePSTNGateway.

No entanto, isso não provou ideal por dois motivos:
 
• **Gerenciamento de sobrecarga**. Descarregar ou descarregar um SBC, por exemplo, altera alguns parâmetros, como habilitar ou desabilitar o bypass de mídia. A alteração da porta requer a alteração de parâmetros em vários locatários (executando Set-CSonlinePSTNGateway), mas é, na verdade, o mesmo SBC. • **Processamento de sobrecarga**. Coletando e monitorando dados de integridade do tronco-opções SIP coletadas de vários troncos lógicos que são, na verdade, o mesmo SBC e o mesmo tronco físico, reduzem o processamento dos dados de roteamento.
 

Com base nesses comentários, a Microsoft está trazendo uma nova lógica para provisionar os troncos para os locatários do cliente.

Duas novas entidades foram introduzidas: • um tronco de portadora registrado no locatário da operadora usando o comando New-CSOnlinePSTNGateway, por exemplo, New-CSOnlinePSTNGateway-FQDN customers.adatum.biz-SIPSignallingport 5068-ForwardPAI $true.
• Um tronco derivado, que não exige registro. É simplesmente um nome de host desejado adicionado do tronco da transportadora. Ele deriva todos os parâmetros de configuração do tronco da transportadora. O tronco derivado não precisa ser criado no PowerShell, e a associação com o tronco da transportadora é baseada no nome FQDN (veja os detalhes abaixo).

Lógica de provisionamento e exemplo.

• As operadoras só precisam configurar e gerenciar um único tronco (tronco de portadora no domínio de transportadora) usando o comando Set-CSOnlinePSTNGateway. No exemplo acima, é adatum.biz; • No locatário do cliente, a transportadora precisa apenas adicionar o FQDN do tronco derivado às políticas de roteamento de voz dos usuários. Não é necessário executar New-CSOnlinePSTNGateway para um tronco.
• O tronco derivado, como o nome sugere, herda ou deriva todos os parâmetros de configuração do tronco da transportadora. Exemplos: • Customers.adatum.biz – o tronco Carrier que precisa ser criado no locatário da operadora.
• Sbc1.customers.adatum.biz – o tronco derivado em um locatário de cliente que não precisa ser criado no PowerShell.  Você pode simplesmente adicionar o nome do tronco derivado no locatário do cliente na política de roteamento de voz online sem criá-lo.

• Todas as alterações feitas em um tronco de transportadora (no locatário de transportadora) são automaticamente aplicadas a troncos derivados. Por exemplo, as operadoras podem alterar uma porta SIP no tronco da transportadora e essa alteração se aplica a todos os troncos derivados. A nova lógica para configurar os troncos simplifica o gerenciamento, pois você não precisa ir para cada locatário e alterar o parâmetro em cada tronco.
• As opções são enviadas apenas ao FQDN do tronco de portadora. O status de integridade do tronco da transportadora é aplicado a todos os troncos derivados e é usado para decisões de roteamento. Saiba mais sobre [as opções de roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).
• A transportadora pode dissipar o tronco de portador e todos os troncos derivados também serão descarregadas. 
 

Migração do modelo anterior para o tronco da operadora
 
Para a migração da implementação atual do modelo hospedado da transportadora para o novo modelo, as operadoras precisarão reconfigurar os troncos para os locatários do cliente. Remova os troncos dos locatários do cliente usando Remove-CSOnluinePSTNGateway (deixando o tronco no locatário da operadora).

Incentivamos a migração para a nova solução o mais rápido possível, pois vamos melhorar o monitoramento e o provisionamento usando a operadora e o modelo de tronco derivado.
 

Consulte as instruções do [fornecedor do SBC](#deploy-and-configure-the-sbc) sobre como configurar o envio do nome FQDN dos subdomínios no cabeçalho do contato.

