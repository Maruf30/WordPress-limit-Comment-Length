add_filter( 'preprocess_comment', 'jeba_wp_comment_length' );
 
function jeba_wp_comment_length($comment) {
if ( strlen( $comment['comment_content'] ) > 4000 ) {
wp_die('Comment is too long. Please keep your comment under 4000 characters.');
}
if ( strlen( $comment['comment_content'] ) < 90 ) {
wp_die('Comment is too short. Please use at least 90 characters.');
}
return $comment;
}
