# eth-quip-client

Here is the current public interface of a Quip contract:

```
contract Quip {

  // events
  
  event QuipAdded( address indexed quipper, string quip );
  event VoterRegistered( address indexed voter );
  event VoteUpdated( address indexed voter, address indexed quipper, uint256 indexed quipIndex, string quip );
  event QuipPaid( address indexed voter, address indexed quipper, uint256 indexed quipIndex, string quip, address payoutToken, uint256 payout );

  // public accessors

  function quipCount()                  public view returns( uint256 count );
  function getQuip(uint256 i)           public view returns( string memory quip, address quipper )
  function hasVoted( address voter )    public view returns ( bool voted );
  function currentVote( address voter ) public view returns( uint256 index );
  function uniformRandomQuip()          public view returns( string memory quip, address quipper )
  function voteWeightedRandomQuip()     public view returns( string memory quip, address quipper )

  // public mutators

  function addQuip( string memory quip )           public returns( uint256 index );
  function vote( uint256 index )                   public;
  function payout( address token, uint256 amount ) public payable;
  
}

```