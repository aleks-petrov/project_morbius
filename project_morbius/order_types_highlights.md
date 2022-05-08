Algorithmic Trading and DMA An introduction to direct access trading strategies by Barry Johnson zliborg Highlights


Chapter I introduces algorithmic trading and direct market access, highlighting their roles  
as core execution methods for institutional trading. 


Chapter 2 introduces the theory of market microstructurc, which focuses solely on the  
mechanics of trading


Chapter 4 focuses on orders.


Chapter 5 covers the various types of trading algorithm in more detail. They are classified  
using three main types, namely impact-driven (e.g. Volume Weighted Average Price  
(VW AP)), cost-driven (e.g. implementation shortfall) and opportunistic (e.g. liquidity  
seeking). 


The "trader's dilemma" of balancing the trade-off between cost and risk is  
visualised using the efficient trading frontier. This is then applied to the selection of trading  
algorithms. The effect of both requirements and asset-specific factors, such as liquidity and  
volatility, are then reviewed.


Chapter 8 considers the intricacies of order placement.


Chapter 9 discusses execution tactics.


short-term forecasting  
models for key market conditions, such as price, volume and volatility, are considered. 


Chapter 11 reviews the main considerations for actually implementing trading strategies,  
with a focus on the required technology. Clearly, order management is a key component, so  
the mechanics of order entry and routing are described


Chapter 12 highlights the potential for portfolio trading.


The two main order types arc market orders and limit orders. In terms of liquidity  
provision, these are complete opposites. Market orders demand liquidity; they require  
immediate trading at the best price available. Whereas limit orders provide liquidity, they act  
as standing orders with inbuilt price limits, which must not be breached (a maximum price  
for buys and a minimum price for sells).


Fundamentally, all trading involves order books,  
whether it is a phone-based OTC transaction or electronic trading via DMA, RFQ or a  
trading algorithm. The only real difference is that for quote-driven markets the order book is  
completely private and belongs to the market maker, whereas for order-driven markets the  
order book is usually centralised and much more transparent.


So the main risk with limit orders is this lack of execution certainty. The market price may  
never reach our limit or even if it does, it may still not be executed since other orders may  
have time priority. This emphasises the need to make a careful choice between the  
requirements for immediacy and price.


Orders that are placed "at the market" correspond to buys with a limit of the best bid or  
sells with a limit at the best offer. The traders who placed these orders are said to be making  
the market. Whilst the most passively priced limit orders are termed "behind the market".  
Their prices mean that they are likely to remain on the order book as standing limit orders  
until the best bid or offer price moves closer to them.


Immediate-or-cancel  
This instruction means any portion of the order that cannot execute immediately against  
existing orders will be cancelled. Any limit price will be enforced, so it will execute as much  
of the required quantity as is available within the specified limit. This can result in only  
partially filling the order.


The IOC instruction  
makes an order grah available liquidity; unlike a market order, it also maintains our price  
limit. Thus, the IOC instruction is often used by algorithms when probing for liquidity.


Fill-or-kill  
A fill-or-kill (FOK) instruction ensures that the order either executes immediately in full or  
not at all. Effectively, it is an IOC instruction combined with a I 00% completion  
requirement. 


Routing instructions  
Execution venues have often catered for additional routing instructions for orders. Thus  
providing a gateway service that allows orders to be routed to other venues as well as  
handling them locally.


Do-not-route  
This instruction ensures that the execution venue will handle the order locally and not route  
it to another venue.


Directed-routing  
Directed-routing provides an associated destination for where the order should be routed to.  
Effectively, the host venue acts as a gateway to route such orders on to their chosen  
destination. The advantage of this approach is that orders may be routed to venues for which  
we do not have a membership, although the host venue will levy routing fees for such orders.


A one-cancels-other (OCO) instruction may be used to make two orders mutually  
exclusive, often this is used to close out of a position. 


A One-triggers-other (OTO) instruction links a supplementary order that will only be  
created upon the successful execution of the main order. 


Market-to-limit orders  
Market-to-limit orders arc indeed a hybrid: a market order with a strong implicit price limit.  
When the order first arrives, it behaves like a market order, seeking liquidity at the hcst  
availahle price, which then becomes its price limit. Unlike a traditional market order, it will  
not just sweep the order hook, instead if there is insufficient liquidity available at the best  
price it will convert into a standing limit order for the residual amount.


Market-with-protection orders  
A market-with-protection order offers the immediacy of a market order together with the  
protection of an inbuilt price limit. Effectively, it is an extension of the market-to-limit order  
with a limit price further away from the last execution price.


Stop orders  
Stop orders are contingent on an activation (or stop) price. Once the market price reaches or  
passes this point, they are transformed into active market orders. 


Trailing stop orders  
A stop order uses an absolute stop price, whereas for a trailing stop order the stop price  
follows (or pegs) favourable moves in the market price. 


Contingent I if-touched orders  
Contingent, or if-touched, orders are effectively the opposite of stops. For foreign exchange,  
they are sometimes called entry orders since they arc generally used to establish positions.  
As with stops, there arc two main types, a market if-touched order and a limit if-touched.


Hidden order types  
Efficient markets need to satisfy the needs of a range of users. Whilst transparency allows  
traders to easily see the available supply and demand, it poses problems for large orders.  
Many markets and venues provide hidden order types that allow traders to work larger orders  
without attracting undue attention.


Hidden orders  
Hidden, undisclosed or non-displayed orders allow traders to participate without giving away  
their position.


Iceberg I reserve orders  
As its name suggests, an iceberg order comprises of a small visible peak and a significantly  
larger hidden volume. The peak (or display) size is configurable, although some venues  
stipulate a minimum, often a percentage of the normal market size (NMS). The visible  
portion of the order is indistinguishable from any other limit order. Each time this displayed  
order is fully executed the venue's trading system splits a new order from the hidden  
volume, until the whole iceberg order is completed. Therefore, each displayed order has  
normal time priority within the order book whilst the hidden volume just has price priority.


Not-held orders  
A not-held order gives complete discretion to the trader about how the order is worked.


Generally, these are used for floor traders since in less transparent markets they will have the  
best knowledge of market conditions.


Discretionary orders  
A discretionary order is a limit order with a slightly more flcxihlc limit price. The limit that  
is displayed on the order book may be augmented by an additional amount when conditions  
arc appropriate. For a buy order, the real price limit is actually the limit price plus this  
discretionary amount, whilst for a sell it is the limit price minus the discretionary. The true  
limit is taken into account only when a matching order comes within the discretionary range.  
Therefore, the order may execute at any price between the displayed limit and the true limit.


Pegged orders  
Pegged orders provide a dynamic limit price; therefore, they can help reduce the inherent  
miss-pricing risk of standing limit orders. A pegged order's limit price may track the best  
bid, offer or even mid price, applying an additional offset amount.


Scale orders  
These may be used to layer child orders throughout the order book at a range of price levels.


Routed order types are becoming more and more common; they can be an important means  
of seeking additional liquidity in today's increasingly fragmented markets.  
As we have already seen, there arc order instructions that cater for routing, allowing  
orders to be sent to specific venues or to stay at a single venue. The natural progression is  
increasingly complex order routing strategies, leading to "smart order routing".


Pass-through orders  
As their name suggests, pass-through orders allow an order to initially pass-through the  
hosting venue on the way to their ultimate destination, often the primary exchange.  
Effectively, they act like two sequential orders, an IOC order at the initial host venue  
followed by an order for the remainder sent to the destination venue.  
This allows an order to consume liquidity from the hosted order hook before routing any  
residual to the chosen destination. In comparison, a standard limit order that sweeps the  
order book will just leave any remainder as a standing order. Therefore, they arc typically  
provided by crossing networks or venues seeking to attract additional liquidity.


Crossing order types  
Many venues already provide orders allowing traders to report off order hook crosses. New  
order types arc also being introduced to allow crossing to actually take place on the order  
book. These have become increasingly important as venues compete for "dark pool"  
liquidity. A nice summary of the order types and flows is provided by Gabriel Butler's  
(2007) review of crossing networks. He classifies the available order types as:  
• Committed orders, firm orders available for immediate execution 
• Uncommitted orders, requiring confirmation before execution 
• Negotiated orders 
• Pass-through orders, routed on their way to another venue


Uncommitted orders  
Uncommitted orders arc similar to indications of interest (IOls) combined with a mechanism  
which enables them to convert to firm orders. They are also sometimes referred to as  
conditional orders, such as on BIDS. 
Uncommitted orders can cross with each other or with firm orders. If a potential cross is  
discovered, the owner will be sent a notification, at which point they can then decide whether  
to convert them to a firm order. This allows investors/traders to leave an uncommitted order  
on the crossing network whilst they try lo work the same order on other venues, knowing  
that they will not get any unexpected fills.


Negotiated orders  
Negotiated orders are used by venues to provide a structured negotiation environment.  
Essentially, they provide a bilateral trading mechanism, as we saw in Chapter 2. Each  
counterparty has an idea of the price and size they are prepared to trade at, so they must  
simply alLcr these until they both agree a deal. Alternatively, they can just walk away since  
there is no obligation to trade.


Alerted orders  
These orders use indications, or alerts, to try to improve the probability of execution by  
broadcasting a message that notifies other market participants of interest in a particular asset.  
This is particularly important for "dark pool" crossing networks where the order book is  
completely invisible.


Order-contingent order types  
Orders can easily be linked together, as we saw using linking instructions. Venues often use  
these to allow orders to either cancel or even trigger another order. Order-contingent orders  
extend this concept by allowing orders to adjust their price and/or size, based on other  
orders


Linked-alternative orders  
This relatively uncommon order type allows a list of alternative orders to be linked so that if  
one order receives fills then the other orders will he reduced by an equivalent amount.


Contingent orders  
Some venues allow even more dynamic linking between orders spanning multiple assets.  
Such contingent orders ensure that a match is only possible when all the other dependent  
orders may also he matched. Typically, this functionality is offered by futures exchanges to  
support spread trading, whereby simultaneous Jong and short positions are traded to try to  
profit from any price differences between two assets. It may also he employed to cater for  
more complex, multi-leg derivatives trading strategies.


Implied orders  
As we saw in the previous section, one way of handling combined orders is to use the current  
market prices and the desired spread to imply their current price and size. Therefore, real  
orders are dynamically adjusted to ensure they keep in line with the required spread.  
Implied orders represent the next evolution of this approach. Spread trading is so  
commonplace for futures that many venues allow them to be traded as standalone orders. So  
we can buy a JUN-SEP spread, just as we might buy or sell the June or September futures  
contracts. This is usually handled by having separate order books dedicated to spread trading  
or handling complex strategics. However, over the last few years more and more venues  
have started to link their standard order books with these complex books. This has allowed  
the creation of implied orders, which are able to span both types of order book. An implied  
spread may be derived from the combination of outright orders for different contracts, whilst  
implied orders may be derived from the combination of spread orders and outright orders


Opportunistic algorithms have evolved from a range of trading strategies. They all take  
advantage of favourable market conditions, whether this is based on price, liquidity or  
another factor.


Whilst pair trading is effectively a market neutral strategy, so risk is less of a concern.  
Instead, the key driver is when the spread or ratio between the assets is favourable.


Since they are so dynamic, opportunistic algorithms tend to be much more closely  
aligned to their underlying execution tactics than other algorithms,


Pair trading involves buying one asset whilst simultaneously selling another. Therefore, this  
is a market neutral strategy; the risks from each asset should hedge or offset each other. This  
makes the trading less affected by market-wide moves, provided that the asset prices are  
surlicicntly correlated. The ideal situation is that the asset we bought increases in price,  
whilst the one we sold falls. Although so long as the profit on one side of the trade outweighs  
any loss on the other side, we should still come out ahead.


A common  
approach for statistical arbitrage is based on the expectation of mean-reversion. This assumes  
that the spread or ratio for the prices of two highly correlated assets will generally oscillate  
around its mean.


As Figure 5-31 shows, when the spread significantly diverts from the mean this signifies a  
trading opportunity. A typical trade entry signal occurs when we expect the spread to return  
to the mean; in this case, the band is based on two standard deviations above and below the  
mean. If the spread continues in this fashion, we can then exit the position at the mean. On  
the other hand, if it fails to revert and continues to diverge then we stand to make losses. This  
may be because the assets are not as correlated as we thought, or the relationship between  
them may have fundamentally changed.  
The quantitative methods for identifying pairs for statistical arbitrage are beyond the scope  
of this hook, since algorithmic trading kicks in once the pairs have already been found. For  
those interested in this topic the book 'Pairs Trading: Quantitative Methods and Analysis' by  
Ganapathy Vidyamurthy (2004) is a good place to start.


For both these examples, we have kept the trading of each asset closely linked. Jn practice,  
this constraint may be loosened, so that each asset may he traded slightly more  
autonomously. Clearly, it is important for the algorithm to incorporate the liquidity of each  
asset, since there could be a substantial difference between the two. In such cases, the  
algorithm will need to make the trading more dependent on the less liquid asset.


Spread/Ratio: Clearly, this acts as the benchmark for the relationship. Note it is often  
necessary to specify how it is based, so whether it is an A-8 spread or A/8 ratio, or B-A or  
BIA. This can be a useful sanity check to ensure the target is correctly defined.


Pairing  
As we saw in Chapter 4, some execution venues support a range of contingent order types  
and conditions; however, the majority of venues do not provide these. Thus, one of the key  
aspects of the pairing tactic is to emulate this behaviour in order to be able to link orders.  
When trading pairs (or baskets) of assets, the trading algorithm focuses on the trigger, i.e.  
whether the ratio or spread is favourable. Ensuring that each of the assets arc successfully  
bought or sold can be delegated to an execution tactic. Since execution cannot be guaranteed,


legging is an important consideration. This is the difference in value in the traded positions  
for each asset. Certainly, legging often drives the execution for these tactics.  
If a reasonable amount of legging is permitted then each order can almost be worked  
separately. The execution tactic can choose to use standard mechanisms, much like any other  
static, price or liquidity-based approach. Only when the legging reaches its limit will it need  
to try to intervene.


Essentially, each order is pegging to what is  
available on the same side of the order book for the other asset. Note that this can also  
involve changing the price as well as the size.  
In turn, these orders are also linked to the outcome of each other, like the contingent  
orders that we saw in Chapter 4.


The relative liquidity of each asset is also important: If one asset is significantly less liquid  
than the other then this becomes a bottleneck. In fact, the orders for the least liquid asset tend  
to drive the whole process.


Price volatility is an important factor for many trading strategics as it helps determine the  
execution prohability of limit orders. Higher volatility increases the likelihood or execution  
since it means the observed price range is likely to be wider. However, it also means orders  
are more likely to become mispriced, and so increases the risk of adverse selection. 


Another forecasting method is to create models based on previous values of volatility. The  
AutoRcgrcssive (AR) model determines the volatility a, from the previous value a,.1 using  
the following formula:

