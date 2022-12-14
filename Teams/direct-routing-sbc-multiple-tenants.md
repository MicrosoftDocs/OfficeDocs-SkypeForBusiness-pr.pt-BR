---
title: Configurar o Controlador de Borda de Sessão – Vários locatários
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar um SBC (Session Border Controller) para atender vários locatários para parceiros Microsoft e/ou operadoras PSTN.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 570709730f7563b30b98626395f6b0a72fc1ac48
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392291"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurar um controlador de borda da sessão para vários locatários

O Roteamento Direto dá suporte à configuração de um SBC (Controlador de Borda de Sessão) para atender a vários locatários.

> [!NOTE]
> Esse cenário foi projetado para parceiros Microsoft e/ou operadoras PSTN, conhecidas como operadoras posteriormente neste documento. Uma operadora vende serviços de telefonia entregues ao Microsoft Teams para seus clientes. 

Uma operadora:
- Implanta e gerencia um SBC em seu datacenter (os clientes não precisam implementar um SBC e recebem serviços de telefonia da operadora no cliente do Teams).
- Interconecta o SBC a vários locatários.
- Fornece serviços de PSTN (Rede Telefônica Comutada Pública) aos clientes.
- Gerencia a qualidade da chamada de ponta a ponta.
- Cobranças separadamente para serviços PSTN.

Microsoft não gerencia operadoras. Microsoft oferece o Sistema telefônico , um PBX (Private Branch Exchange) e um cliente do Teams. Microsoft também certifica telefones e certifica SBCs que podem ser usados com o Sistema telefônico. Antes de escolher uma operadora, verifique se sua escolha tem um SBC certificado e pode gerenciar a qualidade da voz de ponta a ponta.

A seguir estão as etapas de implementação técnica para configurar o cenário.

**Somente operadora:**
1. Implante o SBC e configure-o para o cenário de hospedagem de acordo com as [instruções dos fornecedores certificados do SBC](#deploy-and-configure-the-sbc).
2. Registre um nome de domínio base no locatário da operadora e solicite um certificado curinga.
3. Registre um subdomínio para cada cliente, que faz parte do domínio base.

**Operadora com um administrador global do cliente:**
1. Adicione o nome do subdomínio ao locatário do cliente.
2. Ative o nome do subdomínio.
3. Configure o tronco da operadora para o locatário do cliente e provisione usuários.

*Verifique se você entende as noções básicas de DNS e como o nome de domínio é gerenciado no Microsoft 365. Consulte [Obter ajuda com Microsoft 365 domínios](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) antes de prosseguir.*

## <a name="deploy-and-configure-the-sbc"></a>Implantar e configurar o SBC

Para obter etapas detalhadas sobre como implantar e configurar SBCs para um cenário de hospedagem SBC, consulte a documentação do fornecedor do SBC.

- **Audiocodes:** Consulte [Notas de Configuração de Roteamento Direto](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) para configuração do cenário de hospedagem do SBC, conforme descrito em "Conectando o AudioCodes SBC ao Microsoft Nota de Configuração de Modelo de Hospedagem direta do Teams". 
- **Oracle:** Consulte [Notas de Configuração de Roteamento Direto](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) para configuração do cenário de hospedagem do SBC, conforme descrito na seção "Microsoft". 
- **Comunicações de Faixa de Opções:** Consulte [Guia de Configuração do SBC Core do Ribbon Communications Microsoft Teams](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+MS+Teams+Solution+Guide) para obter documentação sobre como configurar os SBCs da Série Do Ribbon Core. Consulte também [As melhores práticas de faixa de opções – Configurando operadoras para Microsoft O SBC Edge de Roteamento Direto do Teams](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (anynode):** Registre-se no site de [página da Comunidade de Sistemas TE](https://community.te-systems.de/) para obter documentação e exemplos sobre como configurar o SBC de anynode para vários locatários.
- **Metaswitch:** Registre-se no site da [página Comunidade metaswitch](https://manuals.metaswitch.com/MAN39555) para obter documentação sobre como habilitar o SBC do Perimeta para vários locatários.

> [!NOTE]
> Verifique se você sabe como configurar o cabeçalho "Contato". O cabeçalho Contato é usado para localizar o locatário do cliente na mensagem de convite de entrada. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrar um domínio base e subdomínios

Para o cenário de hospedagem, você precisa criar:

- Um nome de domínio base de propriedade da operadora.
- Um subdomínio que faz parte do nome de domínio base em cada locatário do cliente.

No exemplo a seguir:

- O Adatum é uma operadora que atende vários clientes fornecendo serviços de Internet e telefonia.
- Woodgrove Bank, Contoso e Adventure Works são três clientes que têm Microsoft 365 domínios, mas recebem os serviços de telefonia do Adatum.

Os subdomínios **devem** corresponder ao nome FQDN do tronco que será configurado para o cliente e o FQDN no cabeçalho Contato ao enviar o Convite para Microsoft 365. 

Quando uma chamada chega à interface de Roteamento Direto Microsoft 365, a interface usa o cabeçalho Contato para localizar o locatário em que o usuário deve ser pesquisado. O Roteamento Direto não usa pesquisa de número de telefone no Convite, pois alguns clientes podem ter números não DID que podem se sobrepor em vários locatários. Portanto, o nome FQDN no cabeçalho Contato é necessário para identificar o locatário exato para procurar o usuário pelo número de telefone.

*Para obter mais informações sobre como criar nomes de domínio em Microsoft 365 organizações, consulte [Obter ajuda com Microsoft 365 domínios](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

O diagrama a seguir resume os requisitos para base de domínio, subdomínios e cabeçalho de contato.

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="Diagrama mostrando requisitos para domínios e cabeçalho de contato." lightbox="media/direct-routing-1-sbc-requirements.png":::

O SBC requer um certificado para autenticar as conexões. Para o cenário de hospedagem do SBC, a operadora precisa solicitar um certificado com CN e/ou *SAN\* .base_domain (por exemplo, \*.customers.adatum.biz)*. Esse certificado pode ser usado para autenticar conexões com vários locatários atendidos de um único SBC.

A tabela a seguir é um exemplo de uma configuração.


|Novo nome de domínio |Tipo|Registrado  |Certificado CN/SAN para SBC  |Domínio padrão do locatário no exemplo  |Nome FQDN que o SBC deve apresentar no cabeçalho Contato ao enviar chamadas para usuários|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     No locatário da transportadora  |    \*.customers.adatum.biz  |   adatum.biz      |NA, este é um locatário de serviço, sem usuários |
|sbc1.customers.adatum.biz|    Subdomínio  |    Em um locatário do cliente  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomínio | Em um locatário do cliente   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomínio | Em um locatário do cliente |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

Para configurar a base e os subdomínios, siga as etapas descritas abaixo. Este exemplo configura um nome de domínio base (customers.adatum.biz) e um subdomínio para um cliente (sbc1.customers.adatum.biz no locatário do Woodgrove Bank).

> [!NOTE]
> Use sbcX.customers.adatum.biz para habilitar a voz no locatário da operadora; sbcX pode ser qualquer nome de host alfanumérico exclusivo e válido.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrar um nome de domínio base no locatário da operadora

**Essas ações são executadas no locatário da transportadora.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Verifique se você tem direitos apropriados no locatário da transportadora

Você só pode adicionar novos domínios se entrar no Centro de administração do Microsoft 365 como administrador global. 

Para validar a função que você tem, entre no Centro de administração do Microsoft 365 (https://portal.office.com)acesse **Usuários Ativos usuários** >  e verifique se você tem uma função de Administrador Global. 

Para obter mais informações sobre funções de administrador e como atribuir uma função no Microsoft 365, consulte [Sobre funções de administrador](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Adicione um domínio base ao locatário e verifique-o

1. No Centro de administração do Microsoft 365, acesse **Domínios** >  de **instalação** > **Adicionar domínio**.

2. Na caixa **Inserir um domínio que você possui** , digite o FQDN do domínio base. No exemplo a seguir, o domínio base é *customers.adatum.biz*.

3. Click **Next**.

4. Neste exemplo, o locatário já tem adatum.biz como um nome de domínio verificado. O assistente não pedirá verificação adicional porque customers.adatum.biz é um subdomínio para o nome já registrado. No entanto, se você adicionar um FQDN que não foi verificado antes, precisará passar pelo processo de verificação. O processo de verificação é [descrito abaixo](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. Selecione **Avançar** e, na página **Atualizar Configurações DNS** , selecione **Adicionar os registros DNS e** selecione **Avançar**.

6. Na próxima página, desmarque todos os valores (a menos que você queira usar o nome de domínio para Exchange, SharePoint, Teams ou Skype for Business), selecione **Avançar** e selecione **Concluir**. Verifique se seu novo domínio está no status completo de Instalação.

### <a name="activate-the-domain-name"></a>Ativar o nome de domínio

Depois de registrar um nome de domínio, você precisará ativá-lo adicionando pelo menos uma conta de recurso ou usuário licenciado do Teams. As contas aceitáveis serão licenciadas com qualquer uma das seguintes SKU's:

- Conta de usuário com Office 365 E1/E3/E5 ou Microsoft 365 E3/E5.
- Conta de usuário com Office 365 A1/A3/A5 ou Microsoft 365 A1/A3/A5.
- Conta de Usuário com Office 365 F3 ou Microsoft 365 F1/F3.
- Conta de usuário com Office 365 G1/G3/G5 ou Microsoft 365 G3/G5.
- Conta de usuário com Microsoft 365 Business Basic/Standard/Premium.
- Conta de usuário com uma **licença Microsoft Dispositivos Compartilhados do Teams**.
- Conta de recurso com uma **licença Telefonia do Microsoft Teams Conta de Recursos**.

Além disso, o endereço UPN (Nome da Entidade de Usuário) ou Skype for Business endereço SIP local deve usar o mesmo FQDN que o domínio recém-criado.

Para obter mais informações sobre como adicionar usuários em Microsoft 365 organizações, consulte [Obter ajuda com Microsoft 365 domínios](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Por exemplo: test@customers.adatum.biz

![Captura de tela da página de ativação do domínio base.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrar um nome de subdomínio em um locatário do cliente

Você precisará criar um nome de subdomínio exclusivo para cada cliente. Neste exemplo, criaremos um subdomínio sbc1.customers.adatum.biz em um locatário com o nome de domínio padrão woodgrovebank.us.

**Todas as ações abaixo estão no locatário do cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Verifique se você tem direitos apropriados no locatário do cliente

Você só pode adicionar novos domínios se entrar no Centro de administração do Microsoft 365 como administrador global. 

Para validar a função que você tem, entre no Centro de administração do Microsoft 365 (https://portal.office.com)acesse **Usuários Ativos usuários** >  e verifique se você tem uma função de Administrador Global. 

Para obter mais informações sobre funções de administrador e como atribuir uma função no Microsoft 365, consulte [Sobre funções de administrador](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Adicione um subdomínio ao locatário do cliente e verifique-o

1. No Centro de administração do Microsoft 365, acesse **Domínios** >  de **instalação** > **Adicionar domínio**.

2. Na caixa **Inserir um domínio que você possui** , digite o FQDN do subdomínio para esse locatário. No exemplo abaixo, o subdomínio é sbc1.customers.adatum.biz.

3. Selecione **Avançar**.

4. O FQDN nunca foi registrado no locatário. Na próxima etapa, você precisará verificar o domínio. Selecione **Adicionar um registro TXT**. 

5. Selecione **Avançar** e observe o valor TXT gerado para verificar o nome do domínio.

    ![Captura de tela dos registros de texto na página Verificar domínio.](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Crie o registro TXT com o valor da etapa anterior no provedor de hospedagem DNS da operadora.

    Para obter mais informações, consulte [Criar registros DNS em qualquer provedor de hospedagem DNS](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Acesse o Centro de administração do Microsoft 365 do cliente e selecione **Verificar**. 

8. Na próxima página, selecione **Adicionar os registros DNS e** selecione **Avançar**.

9. Na página **Escolher seu serviços online**, desmarque todas as opções e selecione **Avançar**.

10. Selecione **Concluir** na página **Atualizar configurações DNS** .

11. Verifique se o status é **Configuração concluído**.

    ![Captura de tela da página mostrando o status da Instalação concluída.](media/direct-routing-12-sbc-setup-complete.png)

> [!NOTE]
> A URL base e o subdomínio para o cliente individual precisam estar no mesmo locatário para permitir que você adicione um tronco de _rota direta_ .

### <a name="activate-the-subdomain-name"></a>Ativar o nome do subdomínio

Depois de registrar um nome de subdomínio, você precisará ativá-lo adicionando pelo menos uma conta de recurso ou usuário licenciado do Teams. As contas aceitáveis serão licenciadas com qualquer uma das seguintes SKU's:

-   Conta de usuário com Office 365 E1/E3/E5/A3/A5 ou Microsoft 365 E3/E5/A3/A5
-   Conta de Usuário com Office 365 F1/F3 ou Microsoft 365 F1/F3
-   Conta de usuário com planos Microsoft 365 Business Basic/Standard/Premium e G3/G5
-   Conta de usuário com uma **licença Microsoft Dispositivos Compartilhados do Teams**
-   Conta de recurso com uma **licença de conta de recurso Telefonia do Microsoft Teams**

Além disso, o UPN da conta (Nome da Entidade de Usuário) ou Skype for Business endereço SIP local deve usar o mesmo FQDN que o subdomínio recém-criado.

Para obter mais informações sobre como adicionar usuários em Microsoft 365 organizações, consulte [Obter ajuda com Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Por exemplo: test@sbc1.customers.adatum.biz

![Captura de tela da página Ativação do subdomínio.](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Criar um tronco e provisionar usuários

Com a versão inicial do Roteamento Direto, Microsoft exigiu que um tronco fosse adicionado a cada locatário servido (locatário do cliente) usando o cmdlet New-CSOnlinePSTNGateway.

No entanto, esse método não se mostrou ideal por dois motivos:
 
- **Gerenciamento de sobrecarga**. Descarregar ou drenar um SBC, por exemplo, altera alguns parâmetros, como habilitar ou desabilitar o bypass de mídia. A alteração da porta requer a alteração de parâmetros em vários locatários (executando Set-CSOnlinePSTNGateway), mas na verdade é o mesmo SBC. 

-  **Processamento de sobrecarga**. Coleta e monitoramento de dados de integridade do tronco – as opções SIP coletadas de vários troncos lógicos que são, na realidade, o mesmo SBC e o mesmo tronco físico, atrasa o processamento dos dados de roteamento.
 
Com base nesses comentários, Microsoft está trazendo uma nova lógica para provisionar os troncos para os locatários do cliente.

Duas novas entidades foram introduzidas:

- Um tronco de transportadora registrado no locatário da operadora usando o comando New-CSOnlinePSTNGateway. Por exemplo: 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- Um tronco derivado que não requer registro. Ele é simplesmente um nome de host desejado adicionado do tronco do porta-malas. Ele deriva todos os parâmetros de configuração do porta-malas do porta-malas. A associação com o tronco da transportadora baseia-se no nome FQDN (confira detalhes abaixo).

**Lógica de provisionamento e exemplo**

- As operadoras precisam configurar e gerenciar apenas um único tronco (o tronco do porta-malas no domínio do porta-aviões) usando o comando Set-CSOnlinePSTNGateway. No exemplo acima, é adatum.biz.

- No locatário do cliente, a operadora precisa adicionar o FQDN de tronco derivado às rotas de voz. Não há necessidade de executar New-CSOnlinePSTNGateway para um tronco.

- O tronco derivado, como o nome sugere, herda ou deriva todos os parâmetros de configuração do tronco do porta-malas. 

Exemplos:
- Customers.adatum.biz – o tronco da transportadora que precisa ser criado no locatário da transportadora.

- Sbc1.customers.adatum.biz – o tronco derivado em um locatário do cliente. Você pode adicionar o nome do tronco derivado no locatário do cliente nas rotas de voz sem criá-lo.

- A operadora precisará configurar o registro DNS resolvendo o FQDN de tronco derivado para o endereço IP SBC da operadora.

- Todas as alterações feitas em um tronco de transportadora (no locatário da transportadora) são aplicadas automaticamente a troncos derivados. Por exemplo, as transportadoras podem alterar uma porta SIP no tronco do porta-malas e essa alteração se aplica a todos os troncos derivados. Uma nova lógica para configurar os troncos simplifica o gerenciamento, pois você não precisa ir a cada locatário e alterar o parâmetro em cada tronco.

- As opções são enviadas apenas para o FQDN do porta-malas da operadora. O status de integridade do tronco da transportadora é aplicado a todos os troncos derivados e é usado para decisões de roteamento. Saiba mais sobre [as opções de Roteamento Direto](./direct-routing-monitor-and-troubleshoot.md).

- O porta-aviões pode drenar o tronco do porta-malas e todos os troncos derivados também serão drenados. 
 
> [!NOTE]
> As regras de conversão de número aplicadas no tronco da transportadora não se aplicam a troncos derivados. Esse é um problema conhecido. Como uma solução alternativa, as regras de conversão de números devem ser criadas para o locatário de cada cliente.

**Migração do modelo anterior para o tronco da transportadora**
 
Para migração da implementação atual do modelo hospedado da operadora para o novo modelo, as operadoras precisarão reconfigurar os troncos para locatários do cliente. Remova os troncos dos locatários do cliente usando Remove-CSOnlinePSTNGateway (deixando o tronco no locatário da transportadora)-

Incentivamos a migração para a nova solução o mais rápido possível, pois estaremos aprimorando o monitoramento e o provisionamento usando o modelo de porta-malas e o modelo de tronco derivado.
 
Para obter mais informações sobre como configurar o envio do nome FQDN de subdomínios no cabeçalho Contato, consulte as [instruções do fornecedor do SBC](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Considerações sobre como configurar o failover de vários locatários 

Para configurar o failover para um ambiente multilocatário, você precisará fazer o seguinte:

- Para cada locatário, adicione os FQDNs para dois SBCs diferentes. Por exemplo:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Nas Rotas de Voz Online, especifique ambos os SBCs. Se um SBC falhar, a política de roteamento encaminhará chamadas para o segundo SBC.


## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
